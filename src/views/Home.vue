<template>
  <main id="home">
    <section id="home-intro" class="uk-section">
      <div class="uk-container">
          <h1 uk-sticky="offset: 80">
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480">H</span>
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480; delay: 60">e</span>
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480; delay: 120">l</span>
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480; delay: 180">l</span>
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480; delay: 240">o</span>
            <span class="uk-animation-slide-bottom" uk-scrollspy="cls: uk-animation-slide-bottom-small; offset-top: -480; delay: 300">.</span>
          </h1>

          <div class="image" 
          uk-scrollspy="cls: uk-animation-fade; offset-top: -680;"
          style="background-image: url('https://images.unsplash.com/photo-1510936111840-65e151ad71bb?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=3000&q=80')">
            <h1 class="white">Hello.</h1>
          </div>

      </div>
      
    </section>
    <section class="content2">

    </section>
  </main>
</template>

<script>

export default {
  name: 'home'
}
</script>

<style>

h1 {
  font-size: 120px;
}

h1.white {
  color: #FFF;
  margin-top: -40px;
}

#home-intro {
  height: 1800px;
  width: 100%;
  background-color: #FFF;
  margin-top: 360px;
}


.image {
  height: 50vh;
  background-size: cover;
  background-position: center;
}

.content2 {
    height: 500px;
    width: 100%;
    background-color: #000;
}
</style>

