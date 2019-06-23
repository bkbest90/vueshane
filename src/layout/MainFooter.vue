<template>
  <footer
    class="footer"
    :class="{ [`footer-${type}`]: type }"
    :data-background-color="backgroundColor"
  >
    <div class="container">
      <nav>
        <ul>
          <li>
            <img :src="logoImg" style="width:80px;margin-top:-20px"/> 
          </li>
          <li class="sfont">
            <a href="">
              About Us
            </a>
          </li>
          <li>
            <a href="">
              Blog
            </a>
          </li>
          <li>
            <a href="">
              Licenses
            </a>
          </li>
        </ul>
      </nav>
      <div class="copyright">
        &copy; {{ year }}, made with <md-icon>favorite</md-icon> by
        <a href="https://chayanut-resume.firebaseapp.com/" target="_blank">Best</a>
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  props: {
    backgroundColor: String,
    type: String,
    logoImg: {
      type: String,
      default: require("@/assets/img/shane/Shane\'s logo.png")
    }
  },
  data() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>
<style></style>
