<template>
  <div class="main-container">
      <img :src="resolveIconUrl(icon)" alt="icon" class="icon"/>
      <input :placeholder="hint" class="input-holder"/>
      <img :src="accountImage" alt="account" class="account-image"/>
  </div>
</template>

<script>
export default {
    name: "XTranslucentSearch",
    props: {
        icon: String,
        hint: String,
        accountImage: String
    },
    methods:{
        resolveIconUrl: function (path) {
            let images = require.context('../assets/icons', false, /\.svg$|\.png$|.jpeg$/)
            return images("./"+path)
        },
        resolveImageUrl: function (path) {
            let images = require.context('../assets/images', false, /\.svg$|\.jpg$/)
            return images("./"+path)
        } 
    }
}
</script>

<style scoped>
::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
  color: white;
  opacity: 0.7; /* Firefox */
}

:-ms-input-placeholder { /* Internet Explorer 10-11 */
  color: white;
}

::-ms-input-placeholder { /* Microsoft Edge */
  color: white;
}

.main-container{
    background: rgba(255, 255, 255, 0.37);
    border-radius: 1000px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}

.icon{
    height: 25px;
    margin: 8px;
    margin-left: 16px;
    color: white;
}

.account-image{
    height: 30px;
    border-radius: 50%;
    margin: 8px;
    transition: 300ms ease-in-out;
}

.account-image:hover{
    opacity: 0.5;
}

.input-holder{
    outline: none;
    background: none;
    border: none;
    margin-right: 24px;
    font-family: modulus_bold;
    font-size: 1.1em;
    color: white;
}
</style>