<template>
    <div class="main-container">
        <img src="../assets/images/the_x_logo.png" class="thex-logo"/>
        <p class="subtitle">This product belongs to "THE X by aaron"
            , but all the components in it are free to use
             , so feel free to just yoink that from here &#128521;.</p>
        <p class="text-bold">Follow me on social media</p>
        <div class="social-container">
            <x-button
                class="social-icon"
                @click="openLink('https://www.behance.net/aaron_nerox')"
                icn="behance.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">x</x-button>
            <x-button 
                class="social-icon"
                @click="openLink('https://www.facebook.com/Thenerostarx')"
                icn="facebook.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">x</x-button>
            <x-button 
                class="social-icon"
                @click="openLink('https://www.instagram.com/nerostarx')"
                icn="instagram.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">x</x-button>
            <x-button 
                class="social-icon"
                @click="openLink('https://twitter.com/nerostarx')"
                icn="twitter.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">x</x-button>
            <x-button 
                class="social-icon"
                @click="openLink('https://github.com/NeroStarx')"
                icn="github.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">x</x-button>
        </div>
        <p class="text-bold">Built from &#128160; by aaron for the X</p>
    </div>
</template>

<script>
import XButton from "./Xbutton.vue";

export default {
    name: "XFooter",
    components:{
        XButton,
    },
    methods:{
        openLink(link){
            window.open(link)
        }
    }
}
</script>

<style scoped>
.main-container{
    width: 100%;
    background: white;
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
    margin-top: 20px;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
}

.main-container>p.subtitle{
    width: 50%;
    text-align: center;
}

.main-container p.text-bold{
    margin-bottom: 5px;
}

.social-container{
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}


.thex-logo{
    height: 120px;
}

@media only screen and (max-width: 720px){
    .main-container>p.subtitle{
        width: 70%;
        text-align: center;
    }
}
</style>