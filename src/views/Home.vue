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
            <p class="subtitle">The X navigation components</p>
            <x-navigation-bar 
              :icons="iconList"
              @onItemSelected="shout"
            />
            <br>
            <div class="vertical-nav-container">
              <x-side-nav 
                :icons="iconList"
                @onItemSelected="shout"
                :accountImage="url"
              />
              <div class="spacer"></div>
              <x-nav-drawer
                :navItems="itemList"
                @onItemSelected="shout"
                :account="account"
              />
            </div>
          </div>
        </div>
        <div class="x-card component-container">
          <div class="x-card search-container">
            <p class="subtitle">The X CheckBoxes</p>
            <div class="checkbox-container">
              <x-check-box @OnCheckBoxChecked="shout"/>
              <x-check-box @OnCheckBoxChecked="shout"/>
              <x-check-box @OnCheckBoxChecked="shout"/>
            </div>
          </div>
          <div class="x-card">
            <p class="subtitle">Implementation of the checkboxes</p>
            <div class="gallery">
              <image-item v-for="(image,index) in this.imageList" 
                  :key="index" :Url="image"/>
            </div>
          </div>
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
import XSideNav from "../components/XSideNav.vue";
import XNavDrawer from "../components/XNavDrawer.vue";
import XCheckBox from "../components/XcheckBox.vue";
import ImageItem from "../components/ImageItem.vue";

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
    XSideNav,
    XNavDrawer,
    XCheckBox,
    ImageItem,
  },
  data(){
    return{
      url: "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM",
      iconList: ["asterisk.svg","bolt.svg","house.svg","color_palette.svg","star.svg"],
      account: {
        accountImgUrl : "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM",
        accountName: "Aaron nerostarx",
        accountEmail: "kechaoui.haroune@gmail.com"
      },
      itemList: [
        {
          icon: "asterisk.svg",
          name: "Account manager"
        },
        {
          icon: "bolt.svg",
          name: "Rapid messaging"
        },
        {
          icon: "house.svg",
          name: "Home"
        },
        {
          icon: "color_palette.svg",
          name: "Choices"
        },
        {
          icon: "star.svg",
          name: "Favorites"
        },
      ],
      imageList: ["https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"]
    }
  },
  methods: {
    shout(index){
      alert('i am indexed ' + index + ' and selected')
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

.vertical-nav-container{
  width: 90%;
  display: inline-flex;
  flex-direction: row;
  align-items: flex-start;
}

.spacer{
  width: 40px;
}

.checkbox-container{
  display: inline-flex;
  flex-direction: row;
  align-items: center;
}

.gallery{
  display: grid;
  grid-template-columns: auto auto auto;
}
</style>