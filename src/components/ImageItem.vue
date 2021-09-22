<template>
  <div class="main-container">
      <img :src="Url" alt="image" 
      :class="['image', this.isSelected ? 'selected' : '']"/>
      <x-check-box @OnCheckBoxChecked="setSelection" class="checkbox"/>
  </div>
</template>

<script>
import XCheckBox from "./XcheckBox.vue"

export default {
    name: "ImageItem",
    components: {
        XCheckBox,
    },
    props: {
        Url: String,
    },
    data(){
        return {
            isSelected: false,
        }
    },
    methods: {
        setSelection(isCheckBoxChecked){
            this.isSelected = isCheckBoxChecked
        }
    }
}
</script>

<style scoped>
.main-container{
    position: relative;
    height: 100px;
    width: 100px;
    margin: 10px;
}
.checkbox{
    position: absolute;
    left: 0;
    top: 0;
    z-index: 3;
}

.image{
    width:100%;
    height: 100%;
    border-radius: 20px;
    z-index: 1;
}

.selected{
    opacity: 0.7;
}

@media only screen and (max-width: 720px){
    .main-container{
        position: relative;
        height: 85px;
        width: 85px;
        margin: 4px;
    }

    .checkbox{
        width: 15px;
        height: 15px;
        position: absolute;
        left: 0;
        top: 0;
        z-index: 3;
    }

    .image{
        width:100%;
        height: 100%;
        border-radius: 10px;
        z-index: 1;
    }

    .selected{
        opacity: 0.7;
    }
}
</style>