<template>
  <div class="about">
    <SectionTitle :title="title" subtitle="基本資訊" />
    <div>
      <div>轟然作響的歪斜世界裡， 夏油傑需要一個乾淨明亮的地方。</div>
      <div>
        在海明威的同名小說中，「乾淨明亮的地方」近似於維繫尊嚴以求保持站立的意象，
        也暗指戰爭導致世界傾頹、心靈茫然。
        然而對夏油傑來說，他的「乾淨」與「明亮」又是什麼呢，他所希冀的秩序，
        以及兌現秩序的場所又是什麼呢？他需要，他其實不需要，或者他不得不需要？
        五条悟又存在於這個概念的外側還是襯裏、是根基還是威脅、是過去還是未來呢？
      </div>
    </div>
    <div></div>
    <div></div>
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
      title: ["ABOUT."],
    };
  },
};
</script>

<style lang="scss" scoped>
.about {
  height: 100vh;
  width: 50%;
  display: flex;
  flex-direction: column;
  margin-left: 50vw;
}
</style>
