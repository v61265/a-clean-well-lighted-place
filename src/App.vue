<template>
  <div class="wrapper">
    <img class="cover rellax" data-rellax-speed="1" src="./assets/cover.png" />
    <img class="light rellax" data-rellax-speed="10" src="./assets/light.png" />
    <ProgressBar v-show="shouldShowProgressBar" />
    <div id="fullview">
      <About />
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
    };
  },
  mounted() {
    new Rellax(".rellax");
    const scene = this.$scrollmagic
      .scene({
        triggerElement: "#content",
        triggerHook: 0,
        // duration: 1000,
      })
      .on("enter leave", (e) => {
        this.shouldShowProgressBar = e.type === "enter";
      });
    // .addIndicators({ name: "2 (duration: 300)" });

    // Add Scene to controller
    this.$scrollmagic.addScene(scene);
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "./assets/scss/main.css";

.wrapper {
  background: #b48746;
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
