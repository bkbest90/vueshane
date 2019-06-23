<template>
  <div class="wrapper">
    <div class="image-wrapper">
      <img :src="leaf4" alt="leaf4" class="leaf4" v-show="leafShow" />
      <img :src="leaf3" alt="leaf3" class="leaf3" v-show="leafShow" />
      <img :src="leaf2" alt="leaf2" class="leaf2" v-show="leafShow" />
      <img :src="leaf1" alt="leaf1" class="leaf1" v-show="leafShow" />
    </div>
   
   
      <!-- <div class="md-layout">
        <div class="md-layout-item md-size-100 md-small-size-100">
          <h3><small>Tabs on Plain Card</small></h3>
          <nav-tabs-card no-label tabs-plain>
            <template slot="content">
              <md-tabs md-sync-route class="md-danger" md-alignment="left">
                <md-tab id="tab-home" md-label="Home">
                  <p>
                    I think that’s a responsibility that I have, to push
                    possibilities, to show people, this is the level that things
                    could be at. So when you get something that has the name
                    Kanye West on it, it’s supposed to be pushing the furthest
                    possibilities. I will be the leader of a company that ends
                    up being worth billions of dollars, because I got the
                    answers. I understand culture. I am the nucleus.
                  </p>
                </md-tab>

                <md-tab id="tab-pages" md-label="Updates">
                  <p>
                    I will be the leader of a company that ends up being worth
                    billions of dollars, because I got the answers. I understand
                    culture. I am the nucleus. I think that’s a responsibility
                    that I have, to push possibilities, to show people, this is
                    the level that things could be at. I think that’s a
                    responsibility that I have, to push possibilities, to show
                    people, this is the level that things could be at.
                  </p>
                </md-tab>

                <md-tab id="tab-posts" md-label="History">
                  <p>
                    I think that’s a responsibility that I have, to push
                    possibilities, to show people, this is the level that things
                    could be at. I will be the leader of a company that ends up
                    being worth billions of dollars, because I got the answers.
                    I understand culture. I am the nucleus. I think that’s a
                    responsibility that I have, to push possibilities, to show
                    people, this is the level that things could be at.
                  </p>
                </md-tab>
              </md-tabs>
            </template>
          </nav-tabs-card>
        </div>
    </div> -->
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  <circle-menu type="middle-around" :number="4" animate="animated flip" mask='black' circle>
    <button type="button" slot="Btn"></button>
    <a slot="item_1" class="fab fa-twitter fa-lg"></a>
    <a slot="item_2" class="fab fa-weixin fa-lg"></a>
    <a slot="item_3" class="fab fa-weibo fa-lg"></a>
    <a slot="item_4" class="fab fa-github fa-lg"></a>
  </circle-menu>
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
    
    
  <div style="text-align: center">
      <button class="btn-outline-light" style="border-radius:2px; border: 0px;background-color:white">
        <i style="font-size:40px;color:black" class="fab fa-facebook-square"></i>
      </button>
      <button class="btn-outline-light" style="border: 0px;background-color:white">
        <i style="font-size:40px;color:black" class="fab fa-youtube" ></i>
      </button>
      <button class="btn-outline-light" style="border: 0px;background-color:white">
        <i style="font-size:40px;color:black" class="fab fa-instagram"></i>
      </button>
      <button class="btn-outline-light" style="border: 0px;background-color:white">
        <i style="font-size:34px;color:black" class="fas fa-envelope"></i>
      </button>
    </div>
  </div>
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import NavPills from "./components/NavPillsSection";
import Notifications from "./components/NotificationsSection";
import TypographyImages from "./components/TypographyImagesSection";
import JavascriptComponents from "./components/JavascriptComponentsSection";
import { NavTabsCard } from "@/components";

export default {
  components: {
    BasicElements,
    NavPills,
    Notifications,
    TypographyImages,
    JavascriptComponents,
    NavTabsCard
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
  .hideNavigator{
    display: none;
  }
  .marginUp {
    margin-top:80px;
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
@media screen and (min-width: 991px) {
  .marginUp{
    margin-top:100px;
  }
}

</style>
