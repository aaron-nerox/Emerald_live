<template>
  <Home />
</template>

<script>
import Home from "./views/Home.vue";

export default {
  name: "App",
  components: {
    Home,
  },
};
</script>

<style>
@font-face {
  font-family: modulus;
  src: url("./assets/fonts/Modulus.ttf");
}

@font-face {
  font-family: modulus_bold;
  src: url("./assets/fonts/Modulus-Bold.otf");
}

#color-primary{
  background-color: #30F5CA;
}

#color-primary-dark{
  background-color: #3BC0E3;
}

#color-accent{
  background-color: #62fff2;
}

#color-light{
  background-color: #d1fffb;
}

#color-gradient{
  background-image: linear-gradient(308deg,#30F5CA,#3BC0E3);
}

html{
  scroll-behavior: smooth;
}

#app {
  display: grid;
  min-height: 100vh;
  width: 100%;
  background-image: url("./assets/images/background.svg");
  background-repeat: no-repeat;
  background-size: cover;
}

::-webkit-scrollbar{
  width: 12px;
}

::-webkit-scrollbar-track-piece{
  background-color: #fff;
  
}

::-webkit-scrollbar-thumb{
  background: #30F5CA;
  border-radius: 100px;
  transition: 300ms ease-in;
}

::-webkit-scrollbar-thumb:hover{
  background: #3BC0E3;
}

.h1title{
  font-family: modulus_bold;
  font-size: 2.7em;
}

.title{
  font-family: modulus_bold;
  font-size: 2em;
}

.subtitle{
  font-family: modulus_bold;
  font-size: 1.4em;
  line-height: 1.5;
}

.text{
  font-family: modulus;
  font-size: 1.1em;
}

.text-bold{
  font-family: modulus_bold;
  font-size: 1.1em;
}

.x-card{
  background-color: white;
  border-radius: 20px;
  margin: 20px;
  padding: 15px;
  color: #222;
}

@media  only screen and (min-width: 720px) {

  #app {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    
  }

  .h1title{
    font-family: modulus_bold;
    font-size: 2.4em;
  }

  .title{
    font-family: modulus_bold;
    font-size: 1.8em;
  }

  .subtitle{
    font-family: modulus_bold;
    font-size: 1.4em;
    line-height: 1.2;
  }

  .text{
    font-family: modulus;
    font-size: 0.8em;
  }

  .text-bold{
    font-family: modulus_bold;
    font-size: 0.8em;
  }

  .x-card{
    background-color: white;
    border-radius: 20px;
    margin: 10px;
    padding: 10px;
    color: #222;
  }
}
</style>
