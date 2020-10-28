<template>
  <div class="header-container">
    <div class="header">
      <div class="title">
        <span>我的</span>
      </div>
      <div class="menu">
        <div class="menu-item">
          <router-link to="/">首页</router-link>
        </div>
        <div class="menu-item">
          <router-link to="/study">我的学习历程</router-link>
        </div>
        <div class="menu-item">
          <router-link to="/life">我的生活</router-link>
        </div>
        <div>
          <button @click="switchTheme('dark')">Dark Theme</button>
          <button @click="switchTheme('light')">Light Theme</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
  methods: {
    switchTheme(type) {
      window.document.documentElement.setAttribute("data-theme", type);
    }
  }
};
</script>
<style lang="scss" scoped>
@import "../style/mixins";
@import "../style/theme";

.header-container {
  width: 100%;
  height: 100%;
  position: relative;
  @include font_color("font_color1");
  @include background_color("background_color1");
  opacity: 0.6;

  > .header {
    @include flex($justify-content: space-between);
    height: 100%;

    > .title {
      margin-left: 3rem;
      @include font(1.4rem);
    }

    > .menu {
      @include flex($justify-content: flex-end);
      height: 100%;

      > .menu-item {
        margin-right: 2rem;

        > a {
          @include font(1.4rem, 600);
          text-decoration-line: none;
          transition: color 0.2s ease-out, border 0.2s ease-out,
            opacity 0.2s ease-out;
        }

        > a:hover {
        }

        > a.router-link-exact-active {
          @include background_color("background_color3");
          @include box_shadow("box-shadow1");
        }
      }
    }
  }
}

.header-container::after {
  content: "";
  border-bottom: 2px solid #676767;
  width: 100%;
  position: absolute;
  left: 0;
}
</style>
