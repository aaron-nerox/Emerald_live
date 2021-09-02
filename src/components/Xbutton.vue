<template>
  <div :class="[mainClass
  , isDisabled ? inactiveClass : activeClass
  , iconOnly ? 'Square' : '']">
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
    background-image: linear-gradient(308deg,grey,grey);
}

.disabled:hover{
    background-image: linear-gradient(308deg,rgb(83, 83, 83),rgb(83, 83, 83));
}

.enabled{
    background-image: linear-gradient(308deg,#7DBEFA,#0479E6);
}

.enabled:hover{
    background-image: linear-gradient(308deg,#ABD6FF ,#7DBEFA);
}

.Square{
    height: 30px;
    width: 30px;
}

.button-body{
    border-radius: 1000px;
    font-family: modulus_bold;
    font-size: 1.2em;
    color: white;
    padding: 8px;
    margin: 10px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    transition: 300ms ease-in-out;
}

.button-icon{
    height: 20px;
    width: 30px;
    margin: 2px;
}

.content{
    margin-right: 8px;
}

.spacer{
    margin-left: 8px;
}
</style>