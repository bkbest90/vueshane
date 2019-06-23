<template>
  <div class="wrapper">
    <!-- <div class="image-wrapper">
      <img :src="leaf4" alt="leaf4" class="leaf4" v-show="leafShow" />
      <img :src="leaf3" alt="leaf3" class="leaf3" v-show="leafShow" />
      <img :src="leaf2" alt="leaf2" class="leaf2" v-show="leafShow" />
      <img :src="leaf1" alt="leaf1" class="leaf1" v-show="leafShow" />
    </div> -->
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

    <radial-menu
    class="fixedButton"
      style="margin: auto; margin-top: 300px; background-color: white"
      :itemSize="55"
      :radius="100"
      :angle-restriction="180">
        <radial-menu-item 
          v-for="(item, index) in items" 
          :key="index" 
          style="background-color: white" 
          @click="() => handleClick(item)">
          <span>{{item}}</span>
        </radial-menu-item>
      </radial-menu>
      <!-- <div style="color: rgba(0,0,0,0.6); margin-top: 16px;">{{ lastClicked }}</div> -->
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
          <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  </div>
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import NavPills from "./components/NavPillsSection";
import Notifications from "./components/NotificationsSection";
import TypographyImages from "./components/TypographyImagesSection";
import JavascriptComponents from "./components/JavascriptComponentsSection";
import { NavTabsCard } from "@/components";
import { RadialMenu,  RadialMenuItem } from 'vue-radial-menu'

export default {
  components: {
    BasicElements,
    NavPills,
    Notifications,
    TypographyImages,
    JavascriptComponents,
    NavTabsCard,
    RadialMenu,
    RadialMenuItem
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
      items: ['foo', 'bar', 'hello', 'world', 'more', 'items'],
      lastClicked: 'click on something!',
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
    handleClick (item) {
      this.lastClicked = item;
    },
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
@media screen and (min-width: 1025px) {
  .marginUp{
    margin-top:100px;
  }
  .fixedButton {
  position:fixed;
  background:red;
  left:50%;
  top:50%;
}
}
@media screen and (max-width: 1025px) {
  .fixedButton {
  position:fixed;
  background:red;
  left:50%;
  bottom:5%;
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
  .fixedButton {
  position:fixed;
  background:red;
  left:43%;
  bottom:5%;
}
}

@media screen and (max-width: 770px) {
  .fixedButton {
  position:fixed;
  background:red;
  left:48%;
  bottom:5%;
}
}
@media screen and (max-width: 4150px) {
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
  .fixedButton {
  position:fixed;
  background:red;
  left:45%;
  bottom:5%;
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
  .fixedButton {
  position:fixed;
  background:red;
  left:41%;
  bottom:5%;
}
} 


</style>
