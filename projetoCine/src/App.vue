<template>
  <div class="app">
    <header>
      <h1>🎬 CINE BK</h1>
      <button class="botao-carrinho" @click="mostrarCarrinho = !mostrarCarrinho">
        🛒 {{ mostrarCarrinho ? 'Fechar' : 'Carrinho' }}
      </button>
    </header>


    <section class="filmes">
      <div v-for="filme in filmes" :key="filme.id" class="filme">
        <img :src="filme.capa" alt="Capa do filme" />
        <h3>{{ filme.titulo }}</h3>
        <p>{{ filme.sinopse }}</p>
        <p class="preco">R$ {{ filme.preco.toFixed(2) }}</p>
        <button class="botao-adicionar" @click="adicionarAoCarrinho(filme)">Adicionar ao carrinho</button>
      </div>
    </section>

     <!--carrinho-->
    <section v-if="mostrarCarrinho" class="carrinho">
      <h2>🛒 Carrinho de Compras</h2>
      <div v-if="carrinho.items.length === 0">
        <p>Carrinho vazio.</p>
      </div>
      <div v-else>
        <div v-for="item in carrinho.items" :key="item.id" class="item-carrinho">
          <div class="info">
            <strong>{{ item.nome }}</strong>
            <p>R$ {{ item.preco.toFixed(2) }}</p>
            <div class="quantidade">
              <button @click="alterarQuantidade(item, -1)">-</button>
              <span>{{ item.quantidade }}</span>
              <button @click="alterarQuantidade(item, 1)">+</button>
            </div>
            <p>Total: R$ {{ item.valorTotal.toFixed(2) }}</p>
          </div>
          <button class="remover" @click="removerItem(item)">✖</button>
        </div>
        <div class="total">
          <h3>Total: R$ {{ carrinho.total.toFixed(2) }}</h3>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mostrarCarrinho: false,
      filmes: [
        { id: 1,
        titulo: 'Planeta dos Macacos: A origem',
        sinopse: 'Ficção Cietífica/Ação',
        preco: 19.9,
        capa: 'https://br.web.img3.acsta.net/c_310_420/medias/nmedia/18/87/35/38/19874625.jpg' },

        { id: 2,
        titulo: 'Marley & Eu',
        sinopse: 'Infantil/Comédia',
        preco: 29.9,
        capa: 'https://br.web.img2.acsta.net/c_310_420/medias/nmedia/18/87/14/14/20028631.jpg' },

        { id: 3,
          titulo: 'M3GAN',
          sinopse: 'Terror/Ficção',
          preco: 14.9,
          capa: 'https://br.web.img2.acsta.net/c_310_420/pictures/22/10/11/19/20/4591973.jpg' },

        { id: 4,
          titulo: 'Todos Menos Você',
          sinopse: 'Comédia/Romance',
          preco: 24.9,
          capa: 'https://br.web.img3.acsta.net/c_310_420/pictures/23/10/19/16/00/5781108.jpg' },

        { id: 5,
          titulo: 'Meninas Malvadas',
          sinopse: 'Comédia/Romance',
          preco: 9.9,
          capa: 'https://br.web.img2.acsta.net/c_310_420/pictures/210/087/21008705_20130527194056821.jpg' },

          {id: 6,
            titulo: 'A Cinco Passos de Você',
            sinopse: 'Comédia/Romance',
            preco: 9.9,
            capa: 'https://br.web.img3.acsta.net/c_310_420/pictures/19/02/19/15/31/1517190.jpg'
          },

          {id: 7,
            titulo: 'Como Eu Era Antes de Você',
            sinopse: 'Comédia/Romance',
            preco: 9.9,
            capa: 'https://shoppingcidadedasflores.com.br/wp-content/uploads/2024/08/E-assim-que-acaba-500x675.jpg'
          },

          {id: 8,
          titulo: 'Depois do Universo',
          sinopse: 'Comédia/Romance',
          preco: 9.9,
          capa: 'https://br.web.img3.acsta.net/c_310_420/pictures/22/10/27/23/27/5626842.jpg' },

          {id: 9,
            titulo: 'Sexta-Feira 13',
            sinopse: 'Terror/Crime',
            preco: 9.9,
            capa: 'https://br.web.img3.acsta.net/c_310_420/pictures/15/03/10/20/18/175541.jpg'
          },

          {id: 10,
            titulo: 'Os Farofeiros',
            sinopse: 'Comédia',
            preco: 9.9,
            capa: 'https://br.web.img2.acsta.net/c_310_420/pictures/18/01/03/19/24/3938254.jpg'
          },
      ],
      carrinho: {
        items: [],
        frete: 0,
        desconto: 0,
        total: 0
      }
    };
  },
  methods: {
    adicionarAoCarrinho(filme) {
      const itemExistente = this.carrinho.items.find(item => item.id === filme.id);
      if (itemExistente) {
        itemExistente.quantidade++;
        itemExistente.valorTotal = itemExistente.quantidade * itemExistente.preco;
      } else {
        this.carrinho.items.push({
          id: filme.id,
          nome: filme.titulo,
          preco: filme.preco,
          quantidade: 1,
          valorTotal: filme.preco
        });
      }
      this.atualizarTotal();
    },
    alterarQuantidade(item, quantidade) {
      item.quantidade += quantidade;
      if (item.quantidade <= 0) {
        this.removerItem(item);
      } else {
        item.valorTotal = item.quantidade * item.preco;
        this.atualizarTotal();
      }
    },
    removerItem(item) {
      this.carrinho.items = this.carrinho.items.filter(i => i.id !== item.id);
      this.atualizarTotal();
    },
    atualizarTotal() {
      this.carrinho.total = this.carrinho.items.reduce((soma, item) => soma + item.valorTotal, 0);
    }
  }
};
</script>

<style scoped>
body, .app {
  margin: 0;
  background-color: #0d0d0d;
  color: #fff;
  font-family: 'Segoe UI', sans-serif;
}

header {
  background-color: #1a1a1a;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 2px solid #ff0000;
}
/*filmes*/
.botao-carrinho {
  background-color: #ff0000;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  font-weight: bold;
  cursor: pointer;
  border-radius: 4px;
}

.filmes {
  display: flex;
  flex-wrap: wrap;
  padding: 2rem;
  gap: 1.5rem;
  justify-content: center;
}

.filme {
  background-color: #1a1a1a;
  border: 1px solid #333;
  border-radius: 8px;
  padding: 1rem;
  width: 220px;
  text-align: center;
}

.filme img {
  width: 100%;
  border-radius: 4px;
}

.preco {
  color: #ff0000;
  font-weight: bold;
  margin: 0.5rem 0;
}
/*carrinho css*/
.botao-adicionar {
  background-color: #ff0000;
  color: #fff;
  border: none;
  padding: 0.4rem 0.8rem;
  border-radius: 4px;
  cursor: pointer;
}

.carrinho {
  background-color: #1a1a1a;
  padding: 2rem;
  border-top: 2px solid #ff0000;
}

.item-carrinho {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #333;
  padding: 1rem 0;
  align-items: center;
}

.item-carrinho .info {
  flex: 1;
}

.item-carrinho .quantidade button {
  background: #333;
  color: #fff;
  border: none;
  margin: 0 5px;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
  cursor: pointer;
}

.remover {
  background: transparent;
  color: #ff0000;
  border: none;
  font-size: 1.2rem;
  cursor: pointer;
}

.total {
  text-align: right;
  margin-top: 1.5rem;
}
</style>
