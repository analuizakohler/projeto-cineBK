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
        genero: 'Descrição breve 3'
        preco: 9.9,
        quantidade: 0,
        img: '/images/depoisdouniverso.png'
      
        
    },
    {
        id: 4,
        titulo: 'Esposa de Mentirinha',
        genero: 'Romance'
        preco: 9.8,
        quantidade: 0,
        img: '/images/esposadementirinha.png'
        
     
    },
    {
        id: 5,
        titulo: 'Gente Grande',
        genero: 'Comédia'
        preco: 8.7,
        quantidade: 0,
        img: '/images/gentegrande.png'
        
       
    }
    {
      id: 6,
      titulo: 'Insterestelar',
      genero: 'Ficção',
      preco: 7.9,
      quantidade: 0,
      img: '/images/interestelar.png'
    }
];
</script>

<template>
  <h1>CineBK </h1>


  <section id="filmes">
    <h2>Novidades!</h2>
    

  <div class="linha">   
    <ul>
      <li style="background-color: red;" v-for="livro in produtos">
        <img :src="livro.img" alt="">
        <p>{{ livro.titulo }}</p>
        <p>{{ livro.resenha }}</p>
      </li>
    </ul>
  </div>

  </section>

</template>

<style scoped>
.linha ul {
  display: flex;
  
}
.linha2 ul {
  display: flex;
}
ul li{
  flex: 1;
}
li img{
  width: 70%;
  height: 90%;
}
li p {
  font-size: 1.5rem;
  color: palevioletred;
}

</style>
