<template>
  <div id="app">
    <transition name="slide">
      <router-view />
    </transition>
  </div>
</template>
<script>
export default {
  components: {},
  watch: {
    $route(to, from) {
      // console.log(to, from);
    }
  },
  mounted() {
    // console.log(this.router);
  },
  created() {
    // console.log(this.$router);
    // console.log(this.route);
  }
};
</script>
<style lang="scss">
@import "style/styles";
@import "style/common";

#app {
  //background: url("./assets/bg.jpg") no-repeat;
  //background-size: cover;
  //background-position: 50% 50%;
  //-webkit-font-smoothing: antialiased;
  //-moz-osx-font-smoothing: grayscale;
  //text-align: center;
  //@include background_color("background_color1");
  //position: fixed;
  //left: 0;
  //right: 0;
  //top: 0;
  //bottom: 0;
}
</style>
