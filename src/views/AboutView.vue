<template>
  <div class="about">
    <br><br><br>
    <title>About Us</title>
    <link rel="stylesheet" href="" />

    <link
      href="https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap" />
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.6.3/css/all.css"
      integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/"
      crossorigin="anonymous"
    />

    <h1>Informações sobre a Plataforma</h1>
    <div class="row">
      <section class="mapouter col">
        <div class="gmap_canvas">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3654.065263498455!2d-46.6214959237016!3d-23.673623965728037!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce44c3b4727283%3A0x2ac9c7a5fa5b07eb!2sFatec%20Diadema%20-%20Luigi%20Papaiz!5e0!3m2!1spt-BR!2sbr!4v1684101594472!5m2!1spt-BR!2sbr" width="600" height="450" style="border:0;"   loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
      </section>

      <section id="about-us" class="col">
        <div class="sobre">
          <p>
            O BookShifter é uma plataforma inovadora voltada para a venda e doação de livros, com o objetivo de combater a desigualdade educacional no Brasil. Criada com paixão e comprometimento, nossa missão é tornar os livros acessíveis a todos, independentemente de sua situação socioeconômica.
          </p>
          <p>
            Acreditamos que a educação é um direito fundamental de todos os indivíduos e que o acesso a livros de qualidade é essencial para o desenvolvimento pessoal e intelectual. Por meio do BookShifter, proporcionamos uma plataforma onde pessoas podem comprar, vender e doar livros de forma fácil e segura.
          </p>
          <p>
            Nosso foco é incentivar a leitura e promover a igualdade de oportunidades educacionais. Ao disponibilizar livros usados a preços acessíveis e oferecer a possibilidade de doações, ajudamos a ampliar o acesso à leitura para aqueles que não teriam condições de adquirir novos livros.
          </p>
          <p>
            Além disso, o BookShifter também trabalha em parceria com instituições e projetos sociais para levar livros a comunidades carentes e escolas públicas. Acreditamos que a educação transforma vidas e estamos empenhados em contribuir para um futuro mais justo e igualitário.
          </p>
          <p>
            Junte-se a nós nessa jornada de transformação. Acesse o BookShifter, encontre os livros que você deseja e faça parte da nossa missão de acabar com a desigualdade educacional no Brasil.
          </p>
        </div>
      </section>
    </div>
    <section>
      <h1>Our Team</h1>
      <div class="row">
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>Gustavo</h3>
            <p>Desenvolvedor.</p>
          </figcaption>
        </figure>
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>José Anderson</h3>
            <p>Desenvolvedor.</p>
          </figcaption>
        </figure>
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>João</h3>
            <p>Desenvolvedor.</p>
          </figcaption>
        </figure>
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>Douglas</h3>
            <p>Desenvolvedor</p>
          </figcaption>
        </figure>
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>Eduardo</h3>
            <p>Desenvolvedor</p>
          </figcaption>
        </figure>
        <figure>
          <img src="../../public/images/img-45.jpg" alt="" />
          <figcaption class="team-member">
            <h3>Flavio</h3>
            <p>Desenvolvedor</p>
          </figcaption>
        </figure>
      </div>
    </section>
  </div>
</template>

<style scoped>

  .mapouter {
    text-align: right;
    border-radius: 14px;
  }

  .gmap_canvas {
    overflow: hidden;
    background: none !important;
    margin-top: 5px;
    width: 100%;
    border-radius: 14px;
    box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
  }

  .row {
    flex-direction: row;
    flex-wrap: wrap;
    margin: 0 10%;
    
  }

  .col {
    width: 35%;
    margin: 0 10px;
  }

  h1 {
    margin-top: 40px;
    text-align: center;
  }

  #about-us,
  h1 {
    font-family: "Montserrat";
  }

  p {
    text-align: justify;
  }

  figure > img {
    width: 25rem;
    height: 25rem;
    object-fit: cover;
    box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.6);
    border-radius: 7px;
  }
.sobre{
  width: 600px;
  

}
  
</style>
