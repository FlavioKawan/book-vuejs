<template>
  <div class="container">
    <div class="header_home_bg">
      <div class="pxtext">
        <span class="border">Conecte-se com a leitura!</span>
        <p><router-link to="/books">Ver mais</router-link></p>
      </div>
    </div>
    <section>
      <div class="row" style="width: 80%; margin: 0 auto;">
        <div class="col">
          <div class="overlay-image">
            <router-link to="/html">
              <img class="image" src="../../public/images/img-3.jpg" alt="Alt text" />
              <div class="normal">
                <div class="text">Promova a leitura</div>
              </div>
              <div class="hover">
                <img class="image" src="../../public/images/img-4.jpg"/>
                <div class="text">Desapegue com amor</div>
              </div>
            </router-link>
          </div>
        </div>
        <div class="col">
          <div class="overlay-image">
            <div class="bg_opacity">
              <img class="image" src="../../public/images/img-2.jpg"/>
            </div>
            <router-link to="/">
              <div class="normal">
                <div class="text">Livros +</div>
              </div>
              <div class="hover">
                <div class="bg_opacity">
                  <img class="image" src="../../public/images/img-1.jpg" />
                </div>
                <div class="text">Livros +</div>
              </div>
            </router-link>
          </div>
        </div>
      </div>
    </section>
    <section class="preview">
      <h2 v-bind:style="ta_center">Livros de Sucesso</h2>
      <div class="row" style="width: auto; margin: 0 auto;">
        <figure class="item">
          <router-link to="/">
            <img src="../../public/images/img-5.jpg" v-bind:style="w100"/>
            <figcaption>Classificações</figcaption>
          </router-link>
        </figure>
        <figure class="item">
          <router-link to="/">
            <img src="../../public/images/img-7.jpg" v-bind:style="w100" />
            <figcaption>Categorias</figcaption>
          </router-link>
        </figure>
        <figure class="item">
          <img src="../../public/images/img-8.jpg" v-bind:style="w100" />
          <router-link to="/">
            <figcaption>Livros Populares</figcaption>
          </router-link>
        </figure>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  data() {
    return {
      w100vw: {width: "100vw", overflow: "hidden"},
      wAuto: {width: "auto"},
      w100: {width: "100%"},
      ta_center: {textAlign: "center"}
    };
  }
};
</script>

<style>
/* ... */
</style>