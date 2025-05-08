<script setup>

</script>
<template>
  <header>
  <div class="app">
    <h1><span>Cine</span>BK</h1>
    <button class="botaocarrinho" @click= "mostrarCarrinho = !mostrarCarrinho">
      {{ mostrarCarrinho ? 'Fechar' : 'Carrinho' }}
    </button>
  </div>
</header>

<section class="filmes">
  <div v-for="filme in flmes" :key="filme.id" class="filme">
    <img :src="filme.capa" alt="Capa do Filme"/>
    <h3>{{ filme.titulo }}</h3>
    <p>{{ filme.sinopse }}</p>
    <p class="preco">R$ {{ filme.preco.toFixed(2) }}</p>
    <button class="botao-adicionar" @click="adcionarAoCarrinho(filme)">Adcionar ao Carrinho</button>
  </div>
</section>
</template>

<style scoped>
.app h1{
  font-weight: bold;
}
div.app span{
  color: red;
  font-weight: bold;
}

</style>
