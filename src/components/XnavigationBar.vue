<template>
  <div class="main-container">
      <div v-for="(icon,index) in icons" 
            :key="index" 
            class="items-container"
            @click="setSelected(index)">
          <img :src="resolveImageUrl(icon)" 
                alt="icon"
                :class="['nav-icon'
                        ,this.currentSelected === index ? selectedIconClass : '']"/>

          <div v-if="this.currentSelected === index" 
                class="selector-point"></div>
      </div>
  </div>
</template>

<script>
export default {
    name: "XNavigationBar",
    props:{
        icons: Array,
    },
    data(){
        return {
            selectedIconClass: "selected",
            currentSelected: 0
        }
    },
    methods:{
        resolveImageUrl: function (path) {
            let images = require.context('../assets/icons', false, /\.svg$|\.png$/)
            return images("./"+path)
        },
        setSelected: function (index){
            this.currentSelected = index;
            this.$emit('onItemSelected',index)
        }
    }
}
</script>

<style scoped>
.main-container{
    width: 80%;
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
    width: 20%;
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
    transition: 200ms ease-in-out;
}

.nav-icon:hover{
    filter: invert(83%) sepia(23%) saturate(1311%) hue-rotate(98deg) brightness(108%) contrast(92%);
}

.selector-point{
    height: 6px;
    width: 6px;
    margin: 2px;
    border-radius: 50%;
    background-color: #30F5CA;
}

.selected{
    filter: invert(83%) sepia(23%) saturate(1311%) hue-rotate(98deg) brightness(108%) contrast(92%);
}

@media only screen and (max-width: 720px){
    .main-container{
        width: 100%;
        background-color: white;
        border-radius: 20px;
        padding-left: 8px;
        padding-right: 8px;
        padding-top: 8px;
        padding-bottom: 8px;
        display: inline-block;
        align-items: center;
    }

    .items-container{
        width: 20%;
        height: min-content;
        display: inline-flex;
        flex-direction: column;
        align-items: center;
    }
}
</style>