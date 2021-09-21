<template>
  <div class="main-container">
        <img :src="resolveImageUrl(icon)" alt="icon" class="main-icon" />
        <input :type="this.mainType"  
            :placeholder="hint" 
            class="input-style" 
            :class="[textClass]" 
            v-model="input"/>
        <div v-if="this.inputType === 'text'" 
            :class="[mainPointer, PointerClass]"></div>
        <img v-else  
            :src="resolveImageUrl(this.passwordIcon)"
            v-on:click="toggleSwitch()"
            alt="eye icon" class="toggle-icon"/>
  </div>
</template>

<script>
export default {
    name: "XInput",
    props: {
        icon: String,
        hint: String,
        inputType: String
    },
    methods:{
        resolveImageUrl: function (path) {
            let images = require.context('../assets/icons', false, /\.svg$|\.png$/)
            return images("./"+path)
        },
        toggleSwitch: function (){
            if(this.mainType == "text"){
                this.mainType = "password"
                this.passwordIcon = "toggle_visible.svg"
            }else{
                this.mainType = "text"
                this.passwordIcon = "toggle_invisible.svg"
            }
        },
        textSanitize: function (inputText){
            return inputText.includes("@") || 
                inputText.includes("#") || 
                inputText.includes("<") ||
                inputText.includes(">") ||
                inputText.includes("/") ||
                inputText.includes("{") ||
                inputText.includes("}")
        }
    },
    data(){
        return {
            mainPointer: "pointer",
            text: "",
            PointerClass: "neutral",
            textClass: "input-txt-neutral",
            mainType: this.inputType,
            passwordIcon: "toggle_visible.svg"
        }
    },
    computed: {
        input: {
            get(){
                return this.text
            },
            set(newInput){
                this.text = newInput

               if(this.inputType == "text"){
                    this.PointerClass = "verified"
                    this.textClass = "input-txt-verified"
                    if(this.textSanitize(this.text)){
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
    width: 100%;
    background: white;
    border-radius: 1000px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}

.pointer{
    border-radius: 50%;
    height: 20px;
    min-width: 20px;
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
    width: 70%;
    margin: 8px;
    margin-right: 24px;
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

.toggle-icon{
    height: 18px;
    widows: 18px;
    margin: 8px;
    margin-right: 16px;
}
</style>