<script setup>

</script>

<template>
  <head>

  </head>
  <body>


  <header>
 <nav>
            <ul>
                <li>
                    <a href="#">Home</a>
                </li>

                <li>
                    <a href="#">Favoritos</a>
                </li>

                <li>
                    <a href="#">Carrinho</a>
                </li>
            </ul>
        </nav>
  </header>
  <main>


  <section class="banner">
    <div>
      <h1>Seja Bem-Vindo ao CineBK</h1>
      <p>Acesse e veja seus filmes favoritos pelo CineBK por um ótimo preço!</p>
    </div>
    <div>

    </div>
  </section>
</main>
</body>

</template>

<style scoped>
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
</style>
