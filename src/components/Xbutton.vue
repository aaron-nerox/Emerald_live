<template>
  <div :class="[mainClass
  , isDisabled ? inactiveClass : activeClass
  , iconOnly ? 'Square' : 'button-padding']">
      <img v-if="iconShown" :src="resolveImageUrl(icn)" alt="button icon" class="button-icon">
      <div v-else class="spacer"></div>
      <div v-if="textShown" class="content">
          <slot></slot>
      </div>
  </div>
</template>

<script>
export default {
    name: "XButton",
    props: {
        isDisabled: Boolean,
        textOnly: Boolean,
        iconOnly: Boolean,
        icn: String,
    },
    data(){
        return{
            mainClass : "button-body",
            activeClass: "enabled",
            inactiveClass: "disabled",
            iconShown: !this.textOnly,
            textShown: !this.iconOnly
        }
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
.disabled{
    background-image: linear-gradient(308deg,#AAAAAA,#AAAAAA);
}

.disabled:hover{
    background-image: linear-gradient(308deg,#999,#999);
}

.enabled{
    background-image: linear-gradient(308deg,#02E1CE,#3BC0E3);
}

.enabled:hover{
    background-image: linear-gradient(308deg,#62fff2 ,#71ddf8);
}

.Square{
    height: 30px;
    width: 30px;
    padding: 10px;
    display: grid;
    align-content: center;
    justify-content: center;
}

.button-padding{
    width: 120px;
    padding-right: 8px;
    padding-left: 8px;
}

.button-body{
    border-radius: 1000px;
    font-family: modulus_bold;
    font-size: 1.2em;
    color: white;
    margin: 10px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    transition: 300ms ease-in-out;
}

.button-icon{
    height: 25px;
    width: 25px;
    margin: 5px;
}

.content{
    width: 100%;
    margin-right: 5px;
    margin-left: 5px;
    margin-top: 10px;
    margin-bottom: 10px;
    text-align: center;
}
</style>