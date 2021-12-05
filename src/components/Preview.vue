<template>
  <div class="about">
    <SectionTitle :title="title" />
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
      title: ["PREVIEW."],
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
