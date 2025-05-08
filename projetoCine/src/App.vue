<script setup>
const produtos = [
    {
        id: 1,
        titulo: 'A cinco passos de você',
        genero: 'Romance',
        preco:11.89,
        quantidade:0,
        img: '/images/acincopassosdevoce.png'


    },
    {
        id: 2,
        titulo: 'A Culpa é das Estrelas',
        genero: 'Romance',
        preco: 19.99,
        quantidade: 0,
        img: '/images/aculpaédasestrelas.png'

    },
    {
        id: 3,
        titulo: 'Depois do Universo',
        genero: 'Romance',
        preco: 10.99,
        quantidade: 0,
        img: '/images/depoisdouniverso.png'


    },
    {
        id: 4,
        titulo: 'Esposa de Mentirinha',
        genero: 'Romance',
        preco: 8.99,
        quantidade: 0,
        img: '/images/esposadementirinha.png'


    },
    {
        id: 5,
        titulo: 'Gente Grande',
        genero: 'Comédia',
        preco: 8.99,
        quantidade: 0,
        img: '/images/gentegrande.png'


    },
    {
      id: 6,
      titulo: 'Insterestelar',
      genero: 'Ficção',
      preco: 7.99,
      quantidade: 0,
      img: '/images/interestelar.png'
    },
    {
      id: 7,
      titulo: 'Marley e Eu',
      genero: 'Comédia',
      preco: 11.99,
      quantidade: 0,
      img: '/images/marleyeeu.png'
    },
    {
      id: 8,
      titulo: 'Meninas Malvadas',
      genero: 'Comédia/Romance',
      preco: 10.89,
      quantidade: 0,
      img: '/images/meangirls.png'
    },
    {
      id: 9,
      titulo: 'Minha Culpa',
      genero: 'Romance',
      preco: 12.89,
      quantidade: 0,
      img: '/images/minhaculpa.png'
    },
    {
      id: 10,
      titulo: 'Planeta dos Macacos',
      genero: 'Ficção Científica/Ação',
      preco: 8.99,
      quantidade: 0,
      img: '/images/planetadosmacacos.png'
    }


];
</script>

<template>
    <header>
 <nav>
            <ul>
                <li>
                    <a href="#">Home</a>
                </li>

                <li>
                    <a href="carrinho.vue">Carrinho</a>
                </li>
            </ul>
        </nav>
  </header>
  <main>


  <section class="banner">
    <div>
      <h1>Seja Bem-Vindo ao <span>Cine</span>BK</h1>
      <p>Acesse e veja seus filmes favoritos pelo CineBK por um ótimo preço!</p>
    </div>

  </section>
</main>


  <section id="filmes">
    <h2 class="novidades">Novidades!</h2>


  <div class="linha">
    <ul>
      <li style="background-color: white;" v-for="filmes in produtos">
        <img :src="filmes.img" alt="">
        <p class="titulo">{{ filmes.titulo }}</p>
        <p class="gn">{{ filmes.genero }}</p>
        <p class="preco">R${{ filmes.preco }}</p>
        <a href="carrinho.vue">comprar</a>

      </li>
    </ul>
  </div>

  </section>

</template>

<style scoped>
h1 span{
  color: red;
  font-weight: bold;
}
a{
    text-decoration:none;
    color: black;
    list-style-type: none;
}
header{
	margin: 2vw 4vw 0 4vw;
}

header nav ul {
	display: flex;
	justify-content: right;
}
header nav ul li {
	margin: 0 10px 0 10px;
	font-weight: bold;
}

section.banner {
	display: flex;
	padding: 10vw 0 5vw 0;
  margin: 5vw;
}
section.banner h1{
font-weight: bold;
font-size: 2.7rem;

}
section.banner p {
	margin: 2vw 0 2vw 0;
  font-size: 1.4rem;
}
.linha ul {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  padding: 0 2vw;
  list-style: none;

}
.linha p{
  white-space: nowrap;
  font-size: 1.3rem;
}
.linha img {
  flex: 1 1 20vw;
  height: 20vw;
  width: 70%;
}
.linha li {
  width: 20%;
  height: 30vw;
  margin-bottom: 5vw;
}
li img{
  width: 70%;
  height: 90%;
}
li p {
  font-size: 1.1rem;
  color: rgb(0, 0, 0);
}
.titulo{
font-size: 1.5rem;
font-weight: 400;
color: rgb(214, 32, 32);

}

.novidades{
  text-align: center;
  font-size: 1.2rem;
  font-weight: bold;
  margin: 3vw;
}
p.gn{
  color: gray;
  font-size: 0.8rem;

}
p.preco{
  font-size: 1.5rem;
  font-weight: 600;
}
.linha a{
  text-align: center;
  font-size: 1.3rem;
  background-color: red;
  border: 0;
  border-radius: 3px;
  padding: 4px;
  color: white;
  margin-top: 30px;
}

</style>
