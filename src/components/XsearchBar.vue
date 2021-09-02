<template>
  <div class="main-container">
      <img :src="resolveIconUrl(icon)" alt="icon" class="icon"/>
      <input :placeholder="hint" class="input-holder"/>
      <img :src="accountImage" alt="account" class="account-image"/>
  </div>
</template>

<script>
export default {
    name: "XSearch",
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
  color: #7DBEFA;
  opacity: 0.5; /* Firefox */
}

:-ms-input-placeholder { /* Internet Explorer 10-11 */
  color: #7DBEFA;
}

::-ms-input-placeholder { /* Microsoft Edge */
  color: #7DBEFA;
}

.main-container{
    background: white;
    border-radius: 1000px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}

.icon{
    height: 25px;
    margin: 8px;
    margin-left: 16px;
    color: #7DBEFA;
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
    color: #7DBEFA;
}
</style>