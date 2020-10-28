<template>
  <div class="container">
    <section class="home" id="home">
      <div class="content">
        <h2 class="main-title">{{ mainTitle }}</h2>
        <h3 class="sub-title">{{ subTitle }}</h3>
      </div>
      <a href="#introduction" class="scroll-down" @click.prevent="scrollTo"></a>
    </section>
    <Nav />
    <Introduction />
    <Experience />
    <Education />
    <Project />
  </div>
</template>

<script>
import Introduction from "@/views/Intro";
import Experience from "@/views/Experience";
import Education from "@/views/Education";
import Project from "@/views/Project";
import Nav from "@/views/Nav";

export default {
  name: "Home",
  components: {
    Introduction,
    Experience,
    Education,
    Project,
    Nav
  },
  data() {
    return {
      subTitle: "WEB DEVELOPER",
      mainTitle: "WANG ZICHEN"
    };
  },
  methods: {
    scrollTo(){
      const top = document.getElementById('introduction').getBoundingClientRect().top;
      window.scrollTo({top: top, left: 0, behavior: 'smooth'});
    }
  }
};
</script>
<style scoped lang="scss">
@import "../style/mixins";

.container {
  .home {
    background: url("../assets/bg.jpg") no-repeat;
    background-size: cover;
    background-position: 50% 50%;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    height: 100vh;
    width: 100%;
    color: white;
    line-height: 1;
    @include flex();

    > .content {
      > .sub-title {
        @include font(2rem);
        margin-top: 1rem;
        text-shadow: 0px 0px 10px #000000;
      }

      > .main-title {
        @include font(4rem, 600);
        line-height: 1.2;
        text-shadow: 0px 0px 6px white;
      }
    }

    > .scroll-down {
      position: absolute;
      bottom: 5vh;
      left: 50%;
      transform: translate(-50%, 0) rotate(-45deg);
      border-bottom: 2px solid #fff;
      border-left: 2px solid #fff;
      width: 2rem;
      height: 2rem;
      display: block;
      text-align: center;
      animation: fade-move-down 2s ease-in-out infinite;
      @keyframes fade-move-down {
        0% {
          opacity: 0;
          transform: translate(0, -10px) rotate(-45deg);
        }
        50% {
          opacity: 1;
        }
        100% {
          opacity: 0;
          transform: translate(0, 10px) rotate(-45deg);
        }
      }
    }
  }
}
</style>
