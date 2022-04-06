<template>
<div class="container ">

  

  <div class="titulo">
    <h2>Página 1</h2><br>
  </div>
  <div class="h-row">
      <div class="logo">
          <a
              href="https://www.segundamano.mx"
              title="Segundamano México: Anuncios clasificados gratis"
              data-src="https://images.segundamano.mx/api/v1/smmx/images/static/logo_med.svg?rule=web_icon_1x"
              lazy="loaded"
              style="background-image: url('https://images.segundamano.mx/api/v1/smmx/images/static/logo_med.svg?rule=web_icon_1x');"
          ></a>
      </div>
      <br>
      <div class="header-container_general-info">
          <button type="button" class="publish-ad">
              <a title="Ingresar">Ingresar</a>
          </button>
      </div>
  </div>




  <div class="details-modal " v-if="true ">
      <div class="details-modal-close">
        X
      </div>
      <div class="details-modal-title">
        <h1>My details modal</h1>
      </div>
      <div class="details-modal-content">
        <p>
          You can click the X in the corner or click the overlay to close this modal.
          Something like this could be useful as a nice way to show additional information,
          but that's about as far as I would take it. It's just a nice way of styling the details element.
        </p>
      </div>
    </div>


</div>
        
</template>

<script>
export default {
    data() {
        return {
            btnIngresa: false
        }
    },
}
</script>

<style scoped>

.titulo{
  text-align: center;
}

.h-row {
    display: flex;
    margin: 1rem auto;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    position: relative;
    min-height: 5.5rem;
    width: 100%;
    max-width: 1024px;
}

.h-row .publish-ad {
    cursor: pointer;
    background: #ff5859;
    font-size: 1.4rem;
    border: 0;
    margin-left: 2.4rem;
    border-radius: 2px;
    box-shadow: 0 0.1rem 0.2rem 0 rgb(0 0 0 / 30%);
    font-weight: 700;
}
.h-row .publish-ad a {
    color: #fff;
    text-decoration: none;
    padding: 1rem;
    display: inline-block;
}

.logo a {
    background-size: cover;
    background-repeat: no-repeat;
    float: left;
    width: 21rem;
    height: 3rem;
}
</style>