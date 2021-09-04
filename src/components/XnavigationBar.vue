<template>
  <div class="main-container">
      <div v-for="(icon,index) in icons" :key="index" class="items-container">
          <img :src="resolveImageUrl(icon)" alt="icon" class="nav-icon"/>
          <div class="selector-point"></div>
      </div>
  </div>
</template>

<script>
export default {
    name: "XNavigationBar",
    props:{
        icons: Array,
    },
    methods:{
        resolveImageUrl: function (path) {
            let images = require.context('../assets/icons', false, /\.svg$|\.png$/)
            return images("./"+path)
        }
    }
}
</script>

<style scoped>
.main-container{
    width: max-content;
    background-color: white;
    border-radius: 20px;
    padding-left: 16px;
    padding-right: 16px;
    padding-top: 8px;
    padding-bottom: 8px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}

.items-container{
    
    display: inline-flex;
    flex-direction: column;
    align-items: center;
}

.nav-icon{
    height: 25px;
    width: 25px;
    margin-right: 16px;
    margin-left: 16px;
    margin-bottom: 8px;
}

.selector-point{
    height: 6px;
    width: 6px;
    border-radius: 50%;
    background-color: #7DBEFA;
}

.selected{
    filter: invert(79%) sepia(24%) saturate(4313%) hue-rotate(180deg) brightness(101%) contrast(96%);
}
</style>