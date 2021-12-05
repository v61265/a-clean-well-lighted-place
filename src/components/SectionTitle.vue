<template>
  <div class="title">
    <div class="title__title">{{ title[0] }}</div>
    <div class="title__subtitle">{{ subtitle }}</div>
    <div>{{ title[1] }}</div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: Array,
      default: () => [],
    },
    subtitle: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
.title {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  &__title {
    font-family: GFS Didot;
    font-size: 48px;
    line-height: 60px;
    color: #fff;
    transform: translate(5px, 0);
    @media (min-width: 768px) {
      transform: translate(20px, 0);
      font-size: 194px;
      line-height: 242px;
    }
  }
  &__subtitle {
    font-family: Noto Sans JP;
    font-weight: 100;
    font-size: 13px;
    line-height: 19px;
    color: #000;
    transform: translate(0, -50%);
    @media (min-width: 768px) {
      font-weight: 100;
      font-size: 48px;
      line-height: 70px;
    }
  }
}
</style>
