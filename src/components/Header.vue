<template>
    <kinesis-container class="main-header-container">
        <div class="title-container">
            <p class="h1title">THE X DESIGN SYSTEM</p>
            <p class="subtitle">Designed to be simple.</p>
        </div>
        <kinesis-element :strength="10" type="translate" class="logo-view">
            <img src="../assets/images/main_logo.svg" alt="decor" />
        </kinesis-element>
        <a href="#about">
            <kinesis-element :strength="10" type="depth" id="link">
                <img src="../assets/icons/down_arrow.svg" alt="down arrow" class="arrow-btn">
            </kinesis-element>
        </a>
    </kinesis-container>
</template>

<script>
import { KinesisContainer, KinesisElement } from "vue-kinesis";

export default {
  name: "XHeader",
  components: {
    KinesisContainer,
    KinesisElement,
  },
};
</script>

<style scoped>
.main-header-container {
  background-image: url("../assets/images/header_background.png");
  background-size: cover;
  background-position: center;
  width: 100%;
  height: 100vh;
  margin: 0;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.title-container{
    margin-top: 4%;
    margin-bottom: 4%;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
}

.title-container>p.h1title{
    margin: 10px;
    color: white;
}

.title-container>p.subtitle{
    margin: 0px;
    color: white;
}

.logo-view {
  width: 130px;
  margin-bottom: auto;
}

.arrow-btn{
    width: 90px;
    margin: 15px;
}
</style>