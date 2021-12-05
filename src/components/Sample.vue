<template>
  <div class="about">
    <SectionTitle :title="title" subtitle="內文試閱" />
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
    };
  },
};
</script>

<style lang="scss" scoped>
.about {
  height: 100vh;
  display: flex;
  justify-content: flex-end;
}
</style>
