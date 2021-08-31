<template>
  <Main />
</template>

<script>
import Main from "./views/Main.vue";

export default {
  name: "App",
  components: {
    Main,
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

#app {
  background-image: url("./assets/images/background.svg");
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
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
}

.text{
  font-family: modulus;
  font-size: 1.1em;
}
</style>
