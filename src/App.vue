<template>
  <div class="wrapper">
    <div>
      <img
        class="cover rellax"
        data-rellax-speed="1"
        src="./assets/cover.png"
      />
      <img
        class="light rellax"
        data-rellax-speed="10"
        src="./assets/light.png"
      />
    </div>
    <ProgressBar v-show="shouldShowProgressBar && !isMobile" />
    <div id="content" data-rellax-speed="10">
      <About :isMobile="isMobile" />
      <Preview />
      <Sample />
    </div>
  </div>
</template>

<script>
import Rellax from "rellax";
import ProgressBar from "./components/ProgressBar.vue";
import About from "./components/About.vue";
import Preview from "./components/Preview.vue";
import Sample from "./components/Sample.vue";
export default {
  name: "App",
  components: {
    ProgressBar,
    About,
    Preview,
    Sample,
  },
  data() {
    return {
      shouldShowProgressBar: false,
      isMobile: true,
    };
  },
  mounted() {
    new Rellax(".rellax");
    const scene = this.$scrollmagic
      .scene({
        triggerElement: "#content",
        triggerHook: 0,
      })
      .on("enter leave", (e) => {
        this.shouldShowProgressBar = e.type === "enter";
      });
    // .addIndicators({ name: "2 (duration: 300)" });

    // Add Scene to controller
    this.$scrollmagic.addScene(scene);
    if (window.innerWidth > 768) {
      this.isMobile = false;
    }
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "./assets/scss/main.css";

.wrapper {
  background: #b48746;
  overflow: hidden;
  width: 100vw;
  position: relative;
}

.cover {
  max-width: 100vw;
  /* position: fixed; */
  top: 0;
  z-index: -1;
  margin-bottom: 50vh;
}

.light {
  z-index: 10;
  max-width: 160vw;
  position: absolute;
  top: 20vh;
  left: -30vw;
  @media (min-width: 768px) {
    top: 50vh;
  }
}

.progress-bar {
  position: fixed;
  top: 50%;
  left: 10vw;
  transform: translate(0, -50%);
}

.section {
  height: 100vh;
  width: 100%;
}
</style>
