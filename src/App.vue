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
  background-color: #7DBEFA;
}

#color-primary-dark{
  background-color: #0479E6;
}

#color-accent{
  background-color: #ABD6FF;
}

#color-light{
  background-color: #D9EDFF;
}

#color-gradient{
  background-image: linear-gradient(308deg,#7DBEFA,#0479E6);
}

html{
  scroll-behavior: smooth;
}

#app {
  min-height: 100vh;
  background-image: url("./assets/images/background.svg");
  background-repeat: no-repeat;
  background-size: cover;
  display: grid;
}

::-webkit-scrollbar{
  width: 12px;
}

::-webkit-scrollbar-track-piece{
  background-color: #fff;
  
}

::-webkit-scrollbar-thumb{
  background: rgb(137, 237, 255);
  border-radius: 100px;
  transition: 300ms ease-in;
}

::-webkit-scrollbar-thumb:hover{
  background: rgb(0, 217, 255);
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
</style>
