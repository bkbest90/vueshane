<template>
  <div class="wrapper">
    <parallax
      class="section page-header header-filter"
      :style="headerStyle"
    ></parallax>
    <div class="main main-raised">
      <div class="section profile-content">
        <div
          style="margin-top:-100px"
          class="container"
        >
          <div class="md-layout">
            <div
              style="margin-top:-100px"
              class="md-layout-item mx-auto guitar"
            >
              <div class="avatar">
                <img
                  :src="img"
                  class="img-raised rounded-circle img-fluid"
                />
              </div>
              <div class="name">
                <h3 class="title">Model page กำลังทำจ้า!!!</h3>
              </div>
                <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
                <br><br><br><br><br><br><br><br><br><br>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { NavTabsCard } from "@/components";
export default {
  components: {
    NavTabsCard
  },
  bodyClass: "profile-page",
  data() {
    return {
      tabPane1: [
        { image: require("@/assets/img/examples/studio-1.jpg") },
        { image: require("@/assets/img/examples/studio-2.jpg") },
        { image: require("@/assets/img/examples/studio-4.jpg") },
        { image: require("@/assets/img/examples/studio-5.jpg") }
      ],
      tabPane2: [
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/cynthia-del-rio.jpg") },
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/clem-onojegaw.jpg") }
      ],
      tabPane3: [
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/studio-3.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/studio-1.jpg") }
      ]
    };
  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/city-profile.jpg")
    },
    img: {
      type: String,
      default: require("@/assets/img/faces/christian.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="scss" scoped>
.section {
  padding: 0;
}
.marginTab {
  margin: 0px 20px 0 20px;
}
.guitar {
  text-align: center;

  img {
    max-width: 160px;
    width: 100%;
    margin-bottom: 0;
    margin-top: -100px;
  }
  .name {
    margin-top: 60px;
  }
}

.profile-tabs /deep/ {
  .md-card-tabs .md-list {
    justify-content: center;
  }
}
</style>
