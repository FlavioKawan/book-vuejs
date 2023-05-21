<template>

      <!-- Email-btn -->
      <div class="email-suport">
      <router-link to='/' class="suport-icon" target='_blank'>
        <i class="far fa-envelope"></i>
      </router-link>
    </div>  

    <!-- Zap-brn -->
     <!-- Botão whatsapp -->
     <div class="buttonzap">
      <a to='https://api.whatsapp.com/send?phone=5511943560779&' class="icon" target='_blank'>
        <i class="fab fa-whatsapp"></i>
      </a>
    </div>

    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.6.3/css/all.css"
      integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/"
      crossorigin="anonymous"
    />

    <div class="container">
      <footer>
      <div class="row foot">
        <div class="col">
          <h1>Bookshifter</h1>
          <p>
            Conheça mais sobre o nosso mundo!
          </p>
        </div>
        <div class="col">
          <h2>Links</h2>
          <ul>
            <li><router-link to="/">Ver itens</router-link></li>

            <li><router-link to="/">Entre em contato via: WhatsApp e E-mail</router-link></li>
            <li><router-link to="/">Enviar e-mail</router-link></li>
            <li>
              <router-link to="/"
                >Politica de Privacidade</router-link>
            </li>

          </ul>
        </div>
        <div class="col">
          <h2>
            Copyright <sup>©</sup>
            <router-link to="/">
              Bookshifter
            </router-link>
          </h2>
        </div>
      </div>
    </footer>
    <footer id="footer-social">
      <ul class="row foot-icons" style="list-style-type: none;">
        <li>
          <a to="/" target="_blank">
            <i class="fab fa-linkedin fa-3x"></i>
          </a>
        </li>
        <li>
          <a to="/" target="_blank">
            <i class="fab fa-telegram fa-3x"></i>
          </a>
        </li>
        <li>
          <a href="https://github.com/Eduardo-2004" target="_blank">
            <i class="fab fa-github fa-3x"></i>
          </a>
        </li>
      </ul>
   </footer>

    </div>
    
</template>

<style scoped>

.foot {
  margin: 0 10% 0 10%;
}
.container {
  margin: 0;
}

footer {
  width: 100vw;
  background-color: var(--blue);
  color: white;
  border-top: 2px solid white;
}
</style>

<script>
export default {
    name: "Footer"
}

</script>