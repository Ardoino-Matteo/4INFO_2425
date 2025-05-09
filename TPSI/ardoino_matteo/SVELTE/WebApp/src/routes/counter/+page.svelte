<script>
    import Counter from "$lib/components/counter.svelte"
    import Doublecounter from "$lib/components/double.counter.svelte"
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    export let counter = 0;
    function counter_incr() {
        counter += 1;
        emit_event('incr');
    }
    function counter_decr() {
        counter -= 1;
        emit_event('decr');
    }
    function emit_event(tipo) {
        dispatch('contatore', {
            tipo: tipo,
            valore
        })
    }
    let contatore = 0
    let double_contatore = 0
    let numeri = [1,7,2,6,9,10];    
</script>
<h1>Pagina Counter!!!</h1>

<h2>Il valore del contatore vale : {contatore}</h2>
<Counter bind:counter={contatore}/>


{#if contatore % 2 == 0}
<h2 class="sottolineato">Il valore del secondo contatore vale: {double_contatore}</h2>
{:else}
<h2>Il valore del secondo contatore vale: {double_contatore}</h2>
{/if}
<Doublecounter bind:counter={double_contatore}/>

<style>
    /*.rosso{color: red;}
    /*.verde{color: green;}*/
    .sottolineato{text-decoration: underline;}
</style>

<ul>
    {#each numeri as numero,indice}
        <li>numeri[{indice}]:{numero}</li>
    {/each}
</ul>