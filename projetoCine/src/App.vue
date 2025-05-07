<script setup>
const produtos = [
    {
        id: 1,
        titulo: 'A cinco passos de você',
        genero: 'Romance',
        preco:7.1,
        quantidade:0,
        img: '/images/acincopassosdevoce.png'
        
        
    },
    {
        id: 2,
        titulo: 'A Culpa é das Estrelas',
        genero: 'Romance',
        preco: 5.7,
        quantidade: 0,
        img: '/images/aculpaédasestrelas.png'
       
    },
    {
        id: 3,
        titulo: 'Depois do Universo',
        genero: 'Romance',
        preco: 9.9,
        quantidade: 0,
        img: '/images/depoisdouniverso.png'
      
        
    },
    {
        id: 4,
        titulo: 'Esposa de Mentirinha',
        genero: 'Romance',
        preco: 9.8,
        quantidade: 0,
        img: '/images/esposadementirinha.png'
        
     
    },
    {
        id: 5,
        titulo: 'Gente Grande',
        genero: 'Comédia',
        preco: 8.7,
        quantidade: 0,
        img: '/images/gentegrande.png'
        
       
    },
    {
      id: 6,
      titulo: 'Insterestelar',
      genero: 'Ficção',
      preco: 7.9,
      quantidade: 0,
      img: '/images/interestelar.png'
    },
    {
      id: 7,
      titulo: 'Marley e Eu',
      genero: 'Comédia',
      preco: 7.9,
      quantidade: 0,
      img: '/images/marleyeeu.png'
    },
    {
      id: 8,
      titulo: 'Meninas Malvadas',
      genero: 'Comédia/Romance',
      preco: 8.7,
      quantidade: 0,
      img: '/images/meangirls.png'
    },
    {
      id: 9,
      titulo: 'Minha Culpa',
      genero: 'Romance',
      preco: 8.7,
      quantidade: 0,
      img: '/images/minhaculpa.png'
    },
    {
      id: 10,
      titulo: 'Planeta dos Macacos',
      genero: 'Ficção Científica/Ação',
      preco: 8.7,
      quantidade: 0,
      img: '/images/planetadosmacacos.png'
    }


];
</script>

<template>
  <h1>CineBK</h1>


  <section id="filmes">
    <h2>Novidades!</h2>
    

  <div class="linha">   
    <ul>
      <li style="background-color: white;" v-for="filmes in produtos">
        <img :src="filmes.img" alt="">
        <p class="titulo">{{ filmes.titulo }}</p>
        <p>{{ filmes.genero }}</p>
        <p>{{ filmes.preco }}</p>
        <a href="/*carrinho*/">comprar</a>
    
      </li>
    </ul>
  </div>

  </section>

</template>

<style scoped>
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
color: rgb(218, 136, 200);
}

</style>
