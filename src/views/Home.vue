<template>
  <x-header></x-header>
  <section id="about" class="x-card section-container">
    <div class="inner-section-container">
      <img src="../assets/images/logo_image.svg" alt="visual logo" class="about-logo">
      <div class="text-container">
        <p class="title">About the system:</p>
        <p class="subtitle">The X design system came from the need to 
          have a system that is familiar to both dominant mobile 
          platforms "android" and "ios", it is a complete mobile ui
          , designed to be simple, diverse and all inclusive. </p>
      </div>
    </div>
  </section>
</template>

<script>
import XHeader from "../components/Header.vue";

export default {
  name: "Home",
  components: {
    XHeader,
  },
};
</script>

<style scoped>
.section-container{
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.inner-section-container{
  display: inline-flex;
  flex-direction: row;
  align-items: center;
}

.about-logo{
  width: 18%;
  border-radius: 20px;
  margin-right: 15px;
}

.text-container{
  display: inline-flex;
  flex-direction: column;
  align-items: flex-start;
}

.title{
  margin: 0px;
}

</style>