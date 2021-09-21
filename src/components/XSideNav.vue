<template>
  <div class="main-container">
      <div class="account-container">
          <img :src="accountImage" alt="user" class="main-account"/>
          <div class="selector-point"></div>
      </div>
      <div v-for="(icon,index) in icons" 
            :key="index" 
            @click="setSelected(index)">
          <img :src="resolveImageUrl(icon)" 
                alt="icon"
                :class="['nav-icon'
                        ,this.currentSelected === index ? selectedIconClass : '']"/>
      </div>
  </div>
</template>

<script>
export default {
    name: "XSideNav",
    props:{
        icons: Array,
        accountImage: String
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
    width: max-content;
    background-color: white;
    border-radius: 20px;
    padding: 8px;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
}

.nav-icon{
    height: 25px;
    width: 25px;
    margin: 12px;
    transition: 200ms ease-in-out;
}

.nav-icon:hover{
    filter: invert(83%) sepia(23%) saturate(1311%) hue-rotate(98deg) brightness(108%) contrast(92%);
}

.selector-point{
    height: 6px;
    width: 6px;
    margin: 8px;
    border-radius: 50%;
    background-color: #30F5CA;
}

.account-container{
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 50px;
    margin-top: 8px;
}


.main-account{
    height: 25px;
    width: 25px;
    border-radius: 50%;
    transition: 300ms ease-in-out;
}

.main-account:hover{
    opacity: 0.7;
}

.selected{
    filter: invert(83%) sepia(23%) saturate(1311%) hue-rotate(98deg) brightness(108%) contrast(92%);
}
</style>