<script>
  
  import Header from "./lib/Header.svelte";
  let contador = $state(0);
  // let dobroContador = $derived(contador * 2)
  let mensagem = $derived(contador<5?"Menor que 5":"Menor que 10")
  let color = "pink"

  $effect(()=>{
    if(contador == 10 || contador == -1){
      contador = 0;
    }
  })

  function adicionarContador(){
    contador++; 
  }

  function subtrairContador(){
    contador--;
  }
</script>

<!-- <h1>Introdução ao Svelte by {nome.toLocaleUpperCase()} que possui {idade} anos</h1> -->

<main>
  <Header/>
  <h4 style="color:{color}">Contador: {contador}</h4>
  <!-- <h4>Dobro do contador: {dobroContador}</h4> -->
   <h4>{mensagem}</h4>
  <button onclick={adicionarContador}>Adicionar</button>
  <button onclick={subtrairContador}>Subtrair</button>
</main>

<style>
  h1{
    color: black;
  }
</style>