<template>
  <nav class="nav" id="nav">
    <ul class="nav-list">
      <li><a href="#home">Home</a></li>
      <li><a href="#introduction">Introduction</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#education">Education</a></li>
      <li><a href="#project">Project</a></li>
    </ul>
  </nav>
</template>
<script>
export default {
  name: "Nav"
};
</script>
<style lang="scss" scoped>
@import "../style/mixins";

.shown {
  top: 0 !important;
}

.nav {
  box-shadow: 0 0 3px 1px #d2d2d2;
  background: white;
  display: block;
  position: fixed;
  top: -100vh;
  left: 0;
  width: 100vw;
  z-index: 90;
  transition: top 0.8s ease;

  > .nav-list {
    @include flex(row, wrap, space-evenly);
    list-style-type: none;

    > li {
      width: 20%;
      transition: all 0.5s linear;
      text-align: center;
      &:hover {
        background: #0482ff;
        > a {
          color: white;
        }
      }

      > a {
        font-size: 1rem;
        width: 100%;
        height: 100%;
        padding: 10px 10px;
        display: inline-block;
      }
    }
  }
}
</style>
