/* eslint-disable vue/no-unused-components */
/* eslint-disable vue/no-unused-components */
<template>
  <x-header></x-header>
  <br />

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
      <br />
      <p class="title"> Example X color palette</p>
      <div class="color-section-container">
        <div  class="color-item" id="color-primary">
          <p class="text">#30F5CA</p>
        </div>
        <div  class="color-item" id="color-primary-dark">
          <p class="text">#3BC0E3</p>
        </div>
        <div  class="color-item" id="color-accent">
          <p class="text">#62fff2</p>
        </div>
        <div  class="color-item" id="color-light">
          <p class="text">#d1fffb</p>
        </div>
        <div  class="color-item" id="color-gradient">
          <p class="text">Gradient</p>
        </div>
      </div>
    </div>
  </section>

  <section id="examples" class="x-card section-container">
    <div class="inner-section-container2">
      <br />
      <p class="title">Take a look at our components</p>
      <p class="subtitle">These components are more dynamic than you think, as a hint try to interact with them.</p>

      <div class="divider-container">
        <div class="x-card component-container">
          <div class="x-card transparent-container">
            <p class="subtitle">The X interactive buttons</p>
            <div>
              <x-button icn="moon.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="false">
                  Activate
              </x-button>
              <x-button icn="moon.svg" 
                :textOnly="false" 
                :iconOnly="true"
                :isDisabled="true">
                  Activate
              </x-button>
            </div>

            <div>
              <x-button 
                class="button-styling"
                icn="moon.svg" 
                :textOnly="true" 
                :iconOnly="false"
                :isDisabled="false">
                  Activate
              </x-button>
              <x-button 
                class="button-styling"
                icn="moon.svg" 
                :textOnly="true" 
                :iconOnly="false"
                :isDisabled="true">
                  Activate
              </x-button>
            </div>

            <div>
              <x-button 
                class="button-styling"
                icn="moon.svg" 
                :textOnly="false" 
                :iconOnly="false"
                :isDisabled="false">
                  Activate
              </x-button>
              <x-button 
                class="button-styling"
                icn="moon.svg" 
                :textOnly="false" 
                :iconOnly="false"
                :isDisabled="true">
                  Activate
              </x-button>
            </div>
          </div>

          <div class="x-card gradient-container">
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

          <div class="x-card gradient-container">
            <p class="subtitle">The X inputs</p>
            <x-input 
              icon="user.svg"
              hint="input a name here"
              inputType="text"
            />
            <br> <br>
            <x-input 
              icon="user.svg"
              hint="input a password here"
              inputType="password"
            />
          </div>

          <div class="x-card gradient-container">
            <p class="subtitle">The X navigation components</p>
            <x-navigation-bar 
              :icons="iconList"
              @onItemSelected="shout"
            />
            <br /><br />
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
          <div class="x-card gradient-container">
            <p class="subtitle">The X CheckBoxes</p>
            <div class="checkbox-container">
              <x-check-box @OnCheckBoxChecked="shout"/>
              <x-check-box @OnCheckBoxChecked="shout"/>
              <x-check-box @OnCheckBoxChecked="shout"/>
            </div>
          </div>
          <div class="x-card gallery-container">
            <p class="subtitle">Implementation of the checkboxes</p>
            <div class="gallery">
              <image-item v-for="(image,index) in this.imageList" 
                  :key="index" :Url="image"/>
            </div>
          </div>
          <div class="map-container">
            <br/>
            <the-x-map 
              class="map-frame"
              :ApiKey="this.ApiKey"
              :CenterCoords="this.MapCenter"
              :zoom="this.zoomLevel"
              :DefaultUi="this.DefaultUi"
            />
            <br />
          </div>
          <div class="x-card gallery-container">
            <p class="subtitle" align="center">The X backdrops</p>
            <img src="../assets/images/backdrop.png" alt="backdrop" class="backdrop"/>
            <br /><br />
            <img src="../assets/images/extended_backdrop.png" alt="backdrop" class="backdrop"/>
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
import TheXMap from "../components/MapView.vue";

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
    TheXMap,
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
        , "https://i.picsum.photos/id/896/200/200.jpg?hmac=GtnSTSOmlmBRvu2fpraj0-9azTBV0t32V07JLyAVPhM"],
      zoomLevel: 10,
      MapCenter: {lat: 36.728, lng: 3.128},
      DefaultUi: false,
      ApiKey: "AIzaSyAUkx6eFkJ0vy0VusCvkdP47KF0mFdKB5E",
    }
  },
  methods: {
    shout(index){
      console.log("item of index "+index+" was selected")
    },
  },
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

.color-section-container{
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
  width: 100%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.transparent-container{
  background-color: #defffc;
  width: 90%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}



.gradient-container{
  width: 90%;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
  background-image: linear-gradient(308deg,#02E1CE,#3BC0E3);
  color: white;
}

.vertical-nav-container{
  display: inline-flex;
  flex-direction: row;
  align-items: center;
}

.spacer{
  width: 50px;
}

.checkbox-container{
  display: inline-flex;
  flex-direction: row;
  align-items: center;
}

.gallery-container{
  background-color: #defffc;
}

.gallery{
  display: grid;
  grid-template-columns: auto auto auto;
}

.map-container{
  width: 100%;
}

.map-frame{
  width: 87%;
  margin-left: auto;
  margin-right: auto;
  height: 500px;
  padding: 0px;
  border-radius: 20px;
  border: 3px solid white;
}

.backdrop{
  width: 100%;
}

@media only screen and (max-width: 720px){
  .section-container{
    text-align: center;
    width: 80%;
    margin-left: auto;
    margin-right: auto;
  
  }

  .inner-section-container{

    display: inline-flex;
    flex-direction: column;
    align-items: center;
  }

  .color-section-container{
    display: grid;
    grid-template-columns: auto auto;
  }

  .divider-container{
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .about-logo{
    width: 60%;
    border-radius: 20px;
    margin-right: 0px;
    margin-bottom: 30px;
  }

  .text-container{
    width: 95%;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .vertical-nav-container{
    display: inline-flex;
    flex-direction: column;
    align-items: center;
  }

  .spacer{
    height: 30px;
  }

  .gallery{
    width: 90%;
    margin-right: auto;
    margin-left: auto;
    display: grid;
    grid-template-columns: auto auto;
  }

}
</style>