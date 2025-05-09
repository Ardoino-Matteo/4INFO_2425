<script>
    let nome, cognome, età, residenza;
    let confermato = false;
</script>
<h1>Input Page</h1>

Nome <input bind:value={nome}>
Cognome <input bind:value={cognome}>
Età <input bind:value={età}>
Residenza <input bind:value={residenza}>
<br><br>    
Confermato <input type="checkbox" bind:checked={confermato}>

<br><br>
Io sono {nome} {cognome} ed ho {età} anni
<button disabled={!confermato}>Invia</button>
