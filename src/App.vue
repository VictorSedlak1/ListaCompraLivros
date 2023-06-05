<script setup>
import MeuCarrinho from './components/MeuCarrinho.vue';
import ListagemLivro from './components/ListagemLivro.vue';


</script>

<template>
  <h1>Minha livraria</h1>
  <div class="container-geral">
    <meu-carrinho />
    <listagem-livros />
  </div>
</template>

<style scoped>

.container-geral {
  /* display: flex;
  justify-content: space-between; */
  display: grid;
  grid-template-columns: 3fr 1fr;
}



</style>
