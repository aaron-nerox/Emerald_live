<template>
  <div class="main-container">
      <div class="account-container">
          <img :src="account.accountImgUrl" alt="user" class="main-account"/>
          <p class="subtitle">{{account.accountName}}</p>
          <p class="text">{{account.accountEmail}}</p>
      </div>
      <div class="items-list">
          <div v-for="(item,index) in navItems" 
            :key="index"  @click="setSelected(index)"
            :class="['item-container',
            this.currentSelected === index ? selectedIconClass : '']">

                <img :src="resolveImageUrl(item.icon)" 
                    alt="icon"
                    :class="['nav-icon']"/>
                <p class="subtitle">{{item.name}}</p>

            </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "XNavDrawer",
    props:{
        navItems: Array,
        account: Object
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

.account-container{
    width: 95%;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 30px;
}

.account-container>p.subtitle{
    color: #222;
    margin: 0px;
    font-size: 1.1em;
}

.account-container>p.text{
    font-size: 0.8em;
    color: #666;
    margin: 0px;
}


.main-account{
    height: 70px;
    width: 70px;
    margin: 10px;
    border-radius: 50%;
    transition: 300ms ease-in-out;
}

.main-account:hover{
    opacity: 0.7;
}

.items-list{
    width: 95%;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
}

.item-container{
    width: 100%;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    background-color: #dfdfdf4b;
    border-radius: 10px;
    padding: 4px;
    margin: 4px;
    transition: 200ms ease-in-out;
}

.item-container>p.subtitle{
    margin: 0px;
    color: #222;
    font-size: 0.8em;
}

.nav-icon{
    height: 20px;
    width: 20px;
    margin: 4px;
    margin-right: 8px;
    transition: 200ms ease-in-out;
}

.item-container:hover{
    background-color: #d1fffb;
}

.selected{
    background-color: #d1fffb;
}

.selected>p.subtitle{
    color: #30F5CA;
}

.selected>img{
    filter: invert(83%) sepia(23%) saturate(1311%) hue-rotate(98deg) brightness(108%) contrast(92%);
}
</style>