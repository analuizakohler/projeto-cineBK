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
<section v-if="mostrarCarrinho" class="carrinho">
  <h2>Carrinho de Compras</h2>
  <div v-if="carrinho.items.length === 0">
    <p>Carrinho Vazio.</p>
  </div>
  <div v-else>
    <div v-for="item in carrinho.items" :key="item.id" class="item-carrinho">
      <div class="info">
        <strong>{{ item.nome }}</strong>
        <p>R${{ item.preco.toFixed(2) }}</p>
        <div class="quantidade">
          <button @click="alterarQuantidade(item,-1)">-</button>
          <span>{{ item.quantidade }}</span>
          <button @click="alterarQuantidade(item, 1)">+</button>
        </div>
        <p>Total: R${{ item.valorTotal.toFixed(2) }}</p>
      </div>
        <button class="remover" @click="removerItem(item)">remover</button>
    </div>
    <div class="total">
      <h3>Total: R${{ carrinho.total.toFixed(2) }}</h3>
    </div>
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
