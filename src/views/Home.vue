<template>
  <x-header></x-header>
  <section id="about" class="x-card section-container">
    <div class="inner-section-container">
      <img src="../assets/images/logo_image.svg" alt="visual logo" class="about-logo">
      <div class="text-container">
        <p class="title">About the system:</p>
        <p class="subtitle">The X design system came from the need to 
          have a system that is familiar to both dominant mobile 
          platforms "android" and "ios", it is a complete mobile ui
          , designed to be simple, diverse and all inclusive. </p>
      </div>
    </div>
  </section>
  <section id="colors" class="x-card section-container">
    <div class="inner-section-container2">
      <p class="title"> Example X color palette</p>
      <div class="inner-section-container">
        <div  class="color-item" id="color-primary">
          <p class="text">#7DBEFA</p>
        </div>
        <div  class="color-item" id="color-primary-dark">
          <p class="text">#0479E6</p>
        </div>
        <div  class="color-item" id="color-accent">
          <p class="text">#ABD6FF</p>
        </div>
        <div  class="color-item" id="color-light">
          <p class="text">#D9EDFF</p>
        </div>
        <div  class="color-item" id="color-gradient">
          <p class="text">Gradient</p>
        </div>
      </div>
    </div>
  </section>
  <section id="examples" class="x-card section-container">
    <div class="inner-section-container2">
      <p class="title">Take a look at our components</p>
      <div class="divider-container">
        <div class="x-card component-container">
          <div class="x-card button-container">
            <p class="subtitle">The X interactive buttons</p>
            <div>
              <x-button icn="facebook.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">
                  Example
              </x-button>
              <x-button icn="facebook.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="true">
                  Example
              </x-button>
            </div>
            <div>
              <x-button 
                icn="facebook.svg" 
                :textOnly="true" 
                :iconOnly="false"
                :isDisabled="false">
                  Example
              </x-button>
              <x-button icn="facebook.svg" 
                :textOnly="true" 
                :iconOnly="false"
                :isDisabled="true">
                  Example
              </x-button>
            </div>
            <div>
              <x-button icn="facebook.svg" 
                :textOnly="false" 
                :iconOnly="false"
                :isDisabled="false">
                  Example
              </x-button>
              <x-button icn="facebook.svg" 
                :textOnly="false" 
                :iconOnly="false"
                :isDisabled="true">
                  Example
              </x-button>
            </div>
          </div>
          <div class="x-card search-container">
            <p class="subtitle">The X search bars</p>
            <x-search 
            hint="Search for something" 
            icon="search.svg"
            :accountImage="url" />
            <br /><br />
            <x-translucent-search 
            hint="Search for something" 
            icon="search_white.svg"
            :accountImage="url"/>
          </div>
          <div class="x-card search-container">
            <p class="subtitle">The X inputs</p>
            <x-input 
            icon="search.svg"
            hint="input a text here"
            inputType="text"
            />
            <br> <br>
            <x-input 
            icon="search.svg"
            hint="input a password here"
            inputType="password"
            />
          </div>
          <div class="x-card search-container">
            <x-navigation-bar 
              :icons="iconList"
            />
          </div>
        </div>
        <div class="x-card component-container">
          <br/><br/><br/><br/><br/>
        </div>
      </div>
    </div>
  </section>
  <x-footer></x-footer>
</template>

<script>
import XHeader from "../components/Header.vue";
import XFooter from "../components/Footer.vue";
import XButton from "../components/Xbutton.vue";
import XSearch from "../components/XsearchBar.vue";
import XTranslucentSearch from "../components/Xtranslucent.vue";
import XInput from "../components/Xinput.vue";
import XNavigationBar from "../components/XnavigationBar.vue";

export default {
  name: "Home",
  components: {
    XHeader,
    XFooter,
    XButton,
    XSearch,
    XTranslucentSearch,
    XInput,
    XNavigationBar,
  },
  data(){
    return{
      url: "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM",
      iconList: ["asterisk.svg","bolt.svg","house.svg","color_palette.svg","star.svg"],
    }
  }
};
</script>

<style scoped>
.section-container{
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.inner-section-container{
  display: inline-flex;
  flex-direction: row;
  align-items: center;
}

.inner-section-container2{
  width: 100%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.about-logo{
  width: 18%;
  border-radius: 20px;
  margin-right: 15px;
}

.text-container{
  display: inline-flex;
  flex-direction: column;
  align-items: flex-start;
}

.title{
  margin: 0px;
}

.color-item{
  height: 90px;
  width: 90px;
  border-radius: 20px;
  margin: 20px;
  display: grid;
  align-items: center;
  justify-content: center;
  color: white;
  
}

.color-item>p{
  font-family: modulus_bold;
}

.divider-container{
  width: 100%;
  display: inline-flex;
  flex-direction: row;
  align-items: flex-start;
}

.component-container{
  background-color: #D9EDFF;
  width: 100%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.button-container{
  width: 80%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.search-container{
  width: 80%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
  background-color: #7DBEFA;
  color: white;
}
</style>