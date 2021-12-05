<template>
  <div class="progress-bar">
    <div class="progress-bar__anchor">基本資訊</div>
    <div class="progress-bar__anchor">實品</div>
    <div class="progress-bar__anchor">內文試閱</div>
    <div class="progress-bar__anchor">販售情報</div>
    <div class="progress-bar__anchor">特別企劃</div>
  </div>
</template>

<style lang="scss" scoped>
.progress-bar {
  &__anchor {
    font-family: Roboto;
    font-weight: 900;
    font-size: 36px;
    line-height: 42px;
    color: #000000;
    &::before {
      content: "";
      display: inline-block;
      background: #fff;
      width: 48px;
      height: 48px;
      border-radius: 50%;
      transform: translate(-50px, 20%);
    }
  }
  div + div {
    margin-top: 10vh;
    position: relative;
    &::after {
      content: "";
      display: inline-block;
      background: #fff;
      width: 10px;
      height: calc(10vh + 48px);
      position: absolute;
      top: calc(-10vh);
      left: -30px;
    }
  }
}
</style>
