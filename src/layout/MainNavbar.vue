<template>
  <md-toolbar
    id="toolbar"
    md-elevation="0"
    class="md-absolute"
    :class="extraNavClasses"
    :color-on-scroll="colorOncroll"
  >
<!-- For PC -->
    <div class="showOnPC md-toolbar-row md-collapse-lateral">
      
      <div class="md-toolbar-section-start">
        <a href="./">
          <img :src="logoImg" v-if="!this.logoBig||this.$route.path!='/'" href="#/" class="w3-animate-top md-title" style="width:140px;height:65px; margin-top:-5px"/> 
        </a>
      </div>
      <!-- Center Nav Bar -->
      <div style="text-align: center;">
      <img :src="logoImg" v-if="this.logoBig&&this.$route.path=='/'" href="#/" class="w3-animate-top" 
        style="width:226px;height:70px; margin-top:5px"/>
        
          <md-list style="margin-top:9px" class="w3-animate-top"
              v-if="this.logoBig&&this.$route.path=='/'"
            >
          <md-list-item >
            <a href="/">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/'">Home</u>
            <u v-else style="border:0">Home</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/model">
            <p style="color:black;margin: 9px"><u v-if="this.$route.path=='/model'">Models</u><u style="border:0" v-else>Models</u> </p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/customizer">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/customizer'">Customizer</u>
            <u style="border:0" v-else>Customizer</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/about">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/about'">About Shane</u><u v-else style="border:0">About Shane</u> </p>
            </a>
          </md-list-item>
            </md-list>
            </div>
      
      <div class="md-toolbar-section-end">
        
        <md-button
          class="showOnPC md-just-icon md-simple md-toolbar-toggle"
          :class="{ toggled: toggledClass }"
          @click="toggleNavbarMobile()"
        >
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </md-button>

        <div class="md-collapse">
          <div class="md-collapse-wrapper">
            <mobile-menu nav-mobile-section-start="false">
              <!-- Here you can add your items from the section-start of your toolbar -->
            </mobile-menu>
      
            <!-- Fixed Nav Bar -->
            <md-list class="w3-animate-top"
              v-if="!this.logoBig||this.$route.path!='/'"
            >
          <md-list-item >
            <a href="/">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/'">Home</u>
            <u v-else style="border:0">Home</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/model">
            <p style="color:black;margin: 9px"><u v-if="this.$route.path=='/model'">Models</u><u style="border:0" v-else>Models</u> </p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/customizer">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/customizer'">Customizer</u>
            <u style="border:0" v-else>Customizer</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/about">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/about'">About Shane</u><u v-else style="border:0">About Shane</u> </p>
            </a>
          </md-list-item>
            </md-list>
          </div>
        </div>
      </div>
    </div>

<!-- For mobile -->
    <div class="showOnMobile md-toolbar-row md-collapse-lateral">
      <div class="showOnMobile md-toolbar-section-start">
        <a href="./">
        <img :src="logoImg" href="#/" class="w3-animate-top md-title" style="width:140px;height:65px; margin-top:-5px"/> 
        </a>
      </div>
      
      <div class="showOnMobile md-toolbar-section-end">
        <md-button
          class="showOnMobile md-just-icon md-simple md-toolbar-toggle"
          :class="{ toggled: toggledClass }"
          @click="toggleNavbarMobile()"
        >
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </md-button>

        <div class="md-collapse">
          <div class="md-collapse-wrapper">
            <mobile-menu nav-mobile-section-start="false">
            </mobile-menu>

              <md-list class="w3-animate-top"
              v-if="this.logoBig"
            >
              <md-list-item >
            <a href="/">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/'">Home</u>
            <u v-else style="border:0">Home</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/model">
            <p style="color:black;margin: 9px"><u v-if="this.$route.path=='/model'">Models</u><u style="border:0" v-else>Models</u> </p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/customizer">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/customizer'">Customizer</u>
            <u style="border:0" v-else>Customizer</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/about">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/about'">About Shane</u><u v-else style="border:0">About Shane</u> </p>
            </a>
          </md-list-item>
            </md-list>

          <md-list class="w3-animate-top"
              v-else
            >
           <md-list-item >
            <a href="/">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/'">Home</u>
            <u v-else style="border:0">Home</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/model">
            <p style="color:black;margin: 9px"><u v-if="this.$route.path=='/model'">Models</u><u style="border:0" v-else>Models</u> </p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/customizer">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/customizer'">Customizer</u>
            <u style="border:0" v-else>Customizer</u></p>
            </a>
          </md-list-item>

          <md-list-item>
            <a href="#/about">
            <p style="color:black;margin:9px"><u v-if="this.$route.path=='/about'">About Shane</u><u v-else style="border:0">About Shane</u> </p>
            </a>
          </md-list-item>
            </md-list>
          </div>
        </div>
      </div>
    </div>
  </md-toolbar>

</template>
<script>
  import { mdbIcon } from 'mdbvue';
  export default {
    
  }
</script>
<script>
let resizeTimeout;
function resizeThrottler(actualResizeHandler) {
  // ignore resize events as long as an actualResizeHandler execution is in the queue
  if (!resizeTimeout) {
    resizeTimeout = setTimeout(() => {
      resizeTimeout = null;
      actualResizeHandler();

      // The actualResizeHandler will execute at a rate of 15fps
    }, 66);
  }
}
import MobileMenu from "@/layout/MobileMenu";
export default {
  components: {
    MobileMenu
  },
  props: {
    logoImg: {
      type: String,
      default: require("@/assets/img/shane/Shane's logo.png")
    },
    logoImgW: {
      type: String,
      default: require("@/assets/img/shane/Shane's logo white.png")
    },
    type: {
      type: String,
      default: "white",
      validator(value) {
        return [
          "white",
          "default",
          "primary",
          "danger",
          "success",
          "warning",
          "info"
        ].includes(value);
      }
    },
    colorOnScroll: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      extraNavClasses: "",
      toggledClass: false,
      logoBig: true
    };
  },
  computed: {
    showDownload() {
      const excludedRoutes = ["login", "landing", "profile"];
      return excludedRoutes.every(r => r !== this.$route.name);
    }
  },
  methods: {
    showLog() {
      console.log(this.$route.path);
    },
    bodyClick() {
      let bodyClick = document.getElementById("bodyClick");

      if (bodyClick === null) {
        let body = document.querySelector("body");
        let elem = document.createElement("div");
        elem.setAttribute("id", "bodyClick");
        body.appendChild(elem);

        let bodyClick = document.getElementById("bodyClick");
        bodyClick.addEventListener("click", this.toggleNavbarMobile);
      } else {
        bodyClick.remove();
      }
    },
    toggleNavbarMobile() {
      this.NavbarStore.showNavbar = !this.NavbarStore.showNavbar;
      this.toggledClass = !this.toggledClass;
      this.bodyClick();
    },
    handleScroll() {
      let scrollValue =
        document.body.scrollTop || document.documentElement.scrollTop;
      let navbarColor = document.getElementById("toolbar");
      this.currentScrollValue = scrollValue;
      if (this.colorOnScroll > 0 && scrollValue > this.colorOnScroll) {
        this.extraNavClasses = `md-${this.type}`;
        navbarColor.classList.remove("md-transparent");
        this.logoBig = false
      } else {
        this.logoBig = true
        if (this.extraNavClasses) {
          this.extraNavClasses = "";
          navbarColor.classList.add("md-transparent");
        }
      }
    },
    scrollListener() {
      resizeThrottler(this.handleScroll);
    },
    scrollToElement() {
      let element_id = document.getElementById("downloadSection");
      if (element_id) {
        element_id.scrollIntoView({ block: "end", behavior: "smooth" });
      }
    }
  },
  mounted() {
    document.addEventListener("scroll", this.scrollListener);
  },
  beforeDestroy() {
    document.removeEventListener("scroll", this.scrollListener);
  }
};
</script>

<style scoped>
u {
  padding-bottom:3px;
  text-decoration:none;
  border-bottom:2px solid #000;
}
.sfont {
    font-family: "Montserrat", Helvetica, Arial, sans-serif;
}
@media screen and (min-width: 991px) {
.showOnMobile{
  display: none;
}
} 
@media screen and (max-width: 991px) {
.showOnPC{
  display: none;
}
.hideNavigator{
  display: none;
}
} 
</style>
