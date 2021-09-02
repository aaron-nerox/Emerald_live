<template>
  <div class="main-container">
      <img :src="resolveImageUrl(icon)" alt="icon" class="main-icon" />
      <input type="text"  
        :placeholder="hint" 
        class="input-style" 
        :class="[textClass]" 
        v-model="input"/>
      <div :class="[mainPointer, PointerClass]"></div>
  </div>
</template>

<script>
export default {
    name: "XInput",
    props: {
        icon: String,
        hint: String,
    },
    methods:{
        resolveImageUrl: function (path) {
            let images = require.context('../assets/icons', false, /\.svg$|\.png$/)
            return images("./"+path)
        }
    },
    data(){
        return {
            mainPointer: "pointer",
            text: "",
            PointerClass: "neutral",
            textClass: "input-txt-neutral"
        }
    },
    computed: {
        input: {
            get(){
                return this.text
            },
            set(newInput){
                this.text = newInput
                this.PointerClass = "verified"
                this.textClass = "input-txt-verified"
                if(this.text.includes("@")){
                    this.PointerClass = "danger"
                    this.textClass = "input-txt-danger"
                }
                if(this.text.length === 0){
                    this.PointerClass = "neutral"
                    this.textClass = "input-txt-neutral"
                }
            }
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

.pointer{
    border-radius: 50%;
    height: 20px;
    width: 20px;
    margin: 8px;
}

.neutral{
    background : #7DBEFA;
}

.verified{
    background : rgb(36, 255, 36);
}

.danger{
    background: rgb(255, 52, 52);
}

.main-icon{
    height: 25px;
    width: 25px;
    margin: 8px;
}

.input-style{
    margin: 8px;
    outline: none;
    border: none;
    background: transparent;
    font-family: modulus_bold;
    font-size: 1.1em;
}

.input-txt-neutral{
    color: #7DBEFA;
}

.input-txt-verified{
    color: rgb(36, 255, 36);
}

.input-txt-danger{
    color: rgb(255, 52, 52);
}
</style>