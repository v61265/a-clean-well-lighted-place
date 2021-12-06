<template>
  <div>
    <SectionTitle :title="title" subtitle="內文試閱" />
    <div v-show="sampleId" class="cover-sample" @click.self="close">
      <img v-show="sampleId === 1" src="../assets/sample_01.jpg" />
      <img v-show="sampleId === 2" src="../assets/sample_02.jpg" />
      <img v-show="sampleId === 3" src="../assets/sample_03.jpg" />
      <img v-show="sampleId === 4" src="../assets/sample_04.jpg" />
      <img v-show="sampleId === 5" src="../assets/sample_05.jpg" />
    </div>
    <div class="sample">
      <div id="one" class="sample__item" @click="handleClick(1)" />
      <div id="two" class="sample__item" @click="handleClick(2)" />
      <div id="three" class="sample__item" @click="handleClick(3)" />
      <div id="four" class="sample__item" @click="handleClick(4)" />
      <div id="five" class="sample__item" @click="handleClick(5)" />
    </div>
  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
export default {
  components: {
    SectionTitle,
  },
  data() {
    return {
      title: ["SAMPLE."],
      sampleId: 0,
    };
  },
  methods: {
    handleClick(id) {
      this.sampleId = id;
    },
    close() {
      this.sampleId = 0;
    },
  },
};
</script>

<style lang="scss" scoped>
.sample {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  margin-top: 80px;
  @media (min-width: 768px) {
    margin-top: 72px;
  }

  div + div {
    margin-top: 16px;
  }

  &__item {
    width: 320px;
    height: 41px;
    background: url("../assets/sample_default_01.png");
    background-size: cover !important;
    &:hover {
      cursor: pointer;
    }
    @media (min-width: 768px) {
      width: 576px;
      height: 73px;
    }
    @media (min-width: 1200px) {
      width: 852px;
      height: 108px;
    }
  }

  #one {
    background: url("../assets/sample_default_01.png");
    &:hover {
      background: url("../assets/sample_hover_01.png");
    }
  }
  #two {
    background: url("../assets/sample_default_02.png");
    &:hover {
      background: url("../assets/sample_hover_02.png");
    }
  }
  #three {
    background: url("../assets/sample_default_03.png");
    &:hover {
      background: url("../assets/sample_hover_03.png");
    }
  }
  #four {
    background: url("../assets/sample_default_04.png");
    &:hover {
      background: url("../assets/sample_hover_04.png");
    }
  }
  #five {
    background: url("../assets/sample_default_05.png");
    &:hover {
      background: url("../assets/sample_hover_05.png");
    }
  }
}

.cover-sample {
  position: fixed;
  top: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;

  img {
    max-width: 100vw;
  }
}
</style>
