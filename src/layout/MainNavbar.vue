<template>
  <md-toolbar
    id="toolbar"
    md-elevation="0"
    class="md-transparent md-absolute"
    :class="extraNavClasses"
    :color-on-scroll="colorOncroll"
  >
    <div class="md-toolbar-row md-collapse-lateral">
      <div class="md-toolbar-section-start">
        <a href="./">
        <img :src="logoImg" v-if="this.logoWhite" href="#/" class="md-title" style="width:140px;height:65px; margin-top:-5px"/> 
        <img :src="logoImgW" v-else href="#/" class="md-title" style="width:140px;height:65px;margin-top:-17px"/> 
        </a>
      </div>
      <!-- Mobile -->
      <div class="md-toolbar-section-end">
        <md-button
          class="md-just-icon md-simple md-toolbar-toggle"
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
            <!-- Black -->
            <md-list v-if="this.logoWhite||toggledClass==true">
              <md-list-item v-if="this.$route.path!='/Configurator'">
                <i style="color:black" class="material-icons">build</i>
                <p style="margin-top:9px;margin-left:8px">Build your guitar</p>
              </md-list-item>

              <md-list-item style="margin-right:15px">
                <i style="color:black" class="material-icons">cloud_download</i>
                <p style="margin-top:10px;margin-left:9px">Contact Shane</p>
              </md-list-item>


              <md-list-item
                href="https://twitter.com/CreativeTim"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:black;margin-left:50px" class="fab fa-twitter"></i>
                <p class="hidden-lg">Twitter</p>
                <md-tooltip md-direction="bottom"
                  >Follow us on Twitter</md-tooltip
                >
              </md-list-item>
              <md-list-item
                href="https://www.facebook.com/CreativeTim"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:black" class="fab fa-facebook-square"></i>
                <p class="hidden-lg">Facebook</p>
                <md-tooltip md-direction="bottom"
                  >Like us on Facebook</md-tooltip
                >
              </md-list-item>
              <md-list-item
                href="https://www.instagram.com/CreativeTimOfficial"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:black" class="fab fa-instagram"></i>
                <p class="hidden-lg">Instagram</p>
                <md-tooltip md-direction="bottom"
                  >Follow us on Instagram</md-tooltip
                >
              </md-list-item>
            </md-list>

            <!-- White -->
            <md-list style="margin-top:-15px" v-else>
              <!-- <md-list-item>
                <i style="color:white" class="material-icons">content_paste</i>
                <p style="color:white;margin-top:9px;margin-left:6px">Build your guitar</p>
              </md-list-item> -->
              <md-list-item style="margin-right:15px">
                <i style="color:white" class="material-icons">cloud_download</i>
                <p style="color:white;margin-top:10px;margin-left:9px">Contact Shane</p>
              </md-list-item>
              <md-list-item
                href="https://twitter.com/CreativeTim"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:white" class="fab fa-twitter"></i>
                <p style="color:white" class="hidden-lg">Twitter</p>
                <md-tooltip md-direction="bottom"
                  >Follow us on Twitter</md-tooltip
                >
              </md-list-item>
              <md-list-item
                href="https://www.facebook.com/CreativeTim"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:white" class="fab fa-facebook-square"></i>
                <p style="color:white" class="hidden-lg">Facebook</p>
                <md-tooltip md-direction="bottom"
                  >Like us on Facebook</md-tooltip
                >
              </md-list-item>
              <md-list-item
                href="https://www.instagram.com/CreativeTimOfficial"
                target="_blank"
                style="margin-left:-15px;margin-right:18px"
              >
                <i style="color:white" class="fab fa-instagram"></i>
                <p style="color:white" class="hidden-lg">Instagram</p>
                <md-tooltip md-direction="bottom"
                  >Follow us on Instagram</md-tooltip
                >
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
      logoWhite: false
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
        this.logoWhite = true
      } else {
        this.logoWhite = false
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
.sfont {
    font-family: "Montserrat", Helvetica, Arial, sans-serif;
}
</style>
