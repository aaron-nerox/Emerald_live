<template>
  <div class="main-container" @click="toggleCheckBox()">
      <img :src="resolveImageUrl(this.checkMark)" 
            alt="checkbox" 
            class="checkmark"/>
  </div>
</template>

<script>
export default {
    name: "XCheckBox",
    methods: {
        toggleCheckBox(){
            if(!this.isChecked){
                this.checkMark = "checked_checkmark.svg"
                this.isChecked = true
            }else{
                this.checkMark = "filled_checkmark.svg"
                this.isChecked = false
            }
            this.$emit("OnCheckBoxChecked", this.isChecked)
        },
        resolveImageUrl: function (path) {
            let images = require.context('../assets/images', false, /\.svg$|\.png$/)
            return images("./"+path)
        }
    },
    data(){
        return {
            checkMark : "filled_checkmark.svg",
            isChecked : false,
        }
    }
}
</script>

<style scoped>
.main-container{
    height: 25px;
    width: 25px;
    padding: 0px;
    margin: 10px;
}

.checkmark{
    border: 3px solid white;
    height: 25px;
    width: 25px;
    border-radius: 50%;
    margin: 1px;
}

@media only screen and (max-width: 720px){
    .main-container{
        height: 20px;
        width: 20px;
        padding: 0px;
        margin: 10px;
    }

    .checkmark{
        border: 2px solid white;
        height: 20px;
        width: 20px;
        border-radius: 50%;
        margin: 1px;
}
}

</style>