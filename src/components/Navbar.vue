<template>
    <nav>
        <ul>
          <li class="primary-nav"><router-link to="/">Bookshifter</router-link></li>
          <li class="secondary-nav"><router-link to="/">Carrinho</router-link></li>
          <li class="secondary-nav"><router-link to="/about">Sobre o BookShifter</router-link></li>
          <li class="secondary-nav"><router-link to="/">Buscar livros</router-link></li>
          <li class="secondary-nav"><router-link to="/books">Meus livros</router-link></li>
        </ul>
      </nav>
</template>

<script>
export default {
    name: "Navbar"
}

</script>

<style scoped>
:root {
  --blue: #1B3764;
  --lyrics: #fff;
  --bg: red
}

nav>ul>li {
  display: inline-block;
}

nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  z-index: 1;
  background-color: #1B3764;
  overflow: auto;
  padding: 10px 30px 20px 10px;
  border-bottom: 2px solid white;
  font-family: Roboto;
}

.primary-nav {
  float: left;
  font-size: 20px;
}

.primary-nav>a {
  letter-spacing: 5px;
}

.secondary-nav>a {
  letter-spacing: 1px;
  color: var(--lyrics);
  font-family: sans-serif;
  font-size: 16px;
  letter-spacing: 1px;
  padding-right: 20px;
}

.secondary-nav {
    margin-right: 10px;
    margin-left: 10px;
    font-size: 20px;
  float: right;
}

nav>ul>li>a {
  color: black;
  font-family: helvetica;
  text-decoration: none;
}

nav>ul>li>a:hover {
  color: #e2e2e2;
  transition: .7s ease;
}

</style>