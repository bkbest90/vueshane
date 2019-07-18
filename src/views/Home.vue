<template>
  <div class="wrapper">
    <parallax
      class="page-header header-filter"
      :style="headerStyle"
    >
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <div class="brand">
              <p class="h1ForI5 h1ForBig sfont">Shane's guitar shop</p>
              <h3 class=" sfont">Your Life Your Style Be Yourself</h3>
              <md-button
                href="#/Configurator"
                style="margin-top:70px;"
                class="md-success forI5 editBtn md-lg"
              >Try to build your guitar for free</md-button>
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="section section-basic">
        <div class="md-layout-item md-size-100 mx-auto ">
          <carousel
            :per-page="1"
            loop
            :speed="700"
            autoplay
            :autoplay-timeout="4000"
            :mouse-drag="false"
            navigationEnabled
            navigationNextLabel="<i class='material-icons'>keyboard_arrow_right</i>"
            navigationPrevLabel="<i class='material-icons'>keyboard_arrow_left</i>"
          >
            <slide>
              <div class="carousel-caption">
                <h4>
                  <md-icon>location_on</md-icon>
                  Someone who like guitar
                </h4>
              </div>
              <img
                :src="carousel1"
                style="height: 100%;width: 100%"
                alt="carousel1"
              />
            </slide>
            <slide>
              <div class="carousel-caption">
                <h4>
                  <md-icon>location_on</md-icon>
                  Yellowstone National Park, United States
                </h4>
              </div>
              <img
                :src="carousel2"
                alt="carousel2"
              />
            </slide>
            <slide>
              <div class="carousel-caption">
                <h4>
                  <md-icon>location_on</md-icon>
                  Yellowstone National Park, United States
                </h4>
              </div>
              <img
                :src="carousel3"
                alt="carousel3"
              />
            </slide>
          </carousel>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import NavPills from "./components/NavPillsSection";
import Notifications from "./components/NotificationsSection";
import TypographyImages from "./components/TypographyImagesSection";
import JavascriptComponents from "./components/JavascriptComponentsSection";

export default {
  components: {
    BasicElements,
    NavPills,
    Notifications,
    TypographyImages,
    JavascriptComponents
  },
  name: "home",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/shane/lespaul2.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false,
      carousel1: require("@/assets/img/shane/slide-1.jpg"),
      carousel2: require("@/assets/img/shane/slide-2.jpg"),
      carousel3: require("@/assets/img/shane/slide-3.jpg")
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.sfont {
  font-family: "Montserrat", Helvetica, Arial, sans-serif;
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
@media screen and (max-width: 991px) {
  .editBtn {
    width: 80%;
  }
}
@media screen and (max-width: 330px) {
  .h1ForI5 {
    margin-top: -50px;
  }
  .h3ForI5 {
    margin-top: 50px;
    margin-bottom: -50px;
  }
  .forI5 {
    margin-top: -500px;
    width: 100%;
  }
}
</style>
