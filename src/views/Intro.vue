<template>
  <div id="introduction">
    <section class="section-container">
      <div class="section-content">
        <div class="flex-img">
          <img src="../assets/avatar.jpg" alt="" />
        </div>
        <div class="flex-fill">
          <h1>王梓晨 Edward Wang</h1>
          <h3>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="18"
              height="18"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              style="margin-right: 8px;"
            >
              <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
              <circle cx="12" cy="10" r="3"></circle>
            </svg>
            宁波 Ningbo
          </h3>
          <h3 class="icon-container">
            <a
              href="mailto:wzc921215@gmail.com"
              target="_blank"
              title="Email"
              class="social-icon"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
                ></path>
                <polyline points="22,6 12,13 2,6"></polyline>
              </svg>
            </a>
            <a
              href="https://github.com/wzc0415"
              target="_blank"
              title="Github"
              class="social-icon"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                ></path>
              </svg>
            </a>
          </h3>
        </div>
      </div>
    </section>
    <section class="section-container">
      <div class="section-content section-content-no-flex">
        <h2 class="section-title">Introduction</h2>
        <p class="section-description">
          我叫王梓晨，{{ age }}岁，是一名Web前端开发工程师，目前从事于一家跨境电商公司。
        </p>
        <p class="section-description">
          <strong>技能:</strong>
          HTML,CSS,JavaScript,TypeScript,SASS/SCSS,PHP,SqlServer,Git
        </p>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  name: "Introduction",
  data() {
    return {
      age: new Date(new Date() - new Date("1992-12-15")).getFullYear() - 1970
    };
  },
  mounted() {
    document.addEventListener("scroll", this.throttle(this.debounce(this.shownNav, 300),200));
  },
  methods: {
    throttle(func, wait) {
      let timer = null;
      return () => {
        if (!timer) {
          setTimeout(() => {
            timer = null;
            func();
          }, wait);
        }
      };
    },
    debounce(func, wait) {
      let timeout;
      return () => {
        clearTimeout(timeout);
        timeout = setTimeout(func, wait);
      };
    },
    shownNav() {
      const offset = this.$el.getBoundingClientRect();
      console.log(offset);
      const offsetTop = offset.top;
      let nav = document.getElementById("nav");
      if (offsetTop <= 0 && offset.y <= 0) {
        console.log("进入可视区域");
        if (!nav.classList.contains("shown")) {
          nav.classList.add("shown");
        }
        // do something...
      } else {
        console.log("移出可视区域");
        if (nav.classList.contains("shown")) {
          nav.classList.remove("shown");
        }
      }
    }
  }
};
</script>
<style scoped lang="scss">
.flex-img {
  flex: 0 2 20%;

  > img {
    max-width: 100px;
    width: 100%;
    border-radius: 50%;
  }
}

.flex-fill {
  flex: 0 1 80%;
  margin-left: 10px;

  > h1 {
    margin: 10px 0;
  }

  > h3 {
    margin: 10px 0;
  }

  .icon-container > :first-child {
    margin-left: 0 !important;
  }

  .social-icon,
  .social-icon:link,
  .social-icon:visited {
    color: #1556d6;
    cursor: pointer;
    margin-left: 10px;
  }
}
</style>
