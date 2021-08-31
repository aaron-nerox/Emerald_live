<template>
    <div class="main-container">
        <img src="../assets/images/the_x_logo.png" class="thex-logo"/>
        <p class="subtitle">This product belongs to "THE X by aaron"
            , but all the components in it are free to use
             , so feel free to just yoink that from here &#128521;.</p>
        <p class="text-bold">Follow me on social media</p>
        <div class="social-container">
            <a href="https://www.behance.net/aaron_nerox" target="_blank"><img src="../assets/icons/behance.svg" alt="icon" class="social-icon"></a>
            <a href="https://www.facebook.com/Thenerostarx" target="_blank"><img src="../assets/icons/facebook.svg" alt="icon" class="social-icon"></a>
            <a href="https://www.instagram.com/nerostarx" target="_blank"><img src="../assets/icons/instagram.svg" alt="icon" class="social-icon"></a>
            <a href="https://twitter.com/nerostarx" target="_blank"><img src="../assets/icons/twitter.svg" alt="icon" class="social-icon"></a>
            <a href="https://github.com/NeroStarx" target="_blank"><img src="../assets/icons/github.svg" alt="icon" class="social-icon"></a>
        </div>
        <p class="text-bold">Built from &#128160; by aaron for the X</p>
    </div>
</template>

<script>
export default {
    name: "XFooter",
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
    margin-left: auto;
    margin-right: auto;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
}

.social-icon{
    width: 30px;
    display: inline-block;
    background-color: #ABD6FF;
    margin: 10px;
    padding: 5px;
    border-radius: 1000px;
    transition: 300ms ease-in-out;
}

.social-icon:hover{
    background-color: #7DBEFA;
}

.thex-logo{
    height: 120px;
}
</style>