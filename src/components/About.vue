<template>
  <div>
    <SectionTitle :title="title" subtitle="基本資訊" />
    <div class="about">
      <div class="container">
        <div class="about__description">
          <div class="about__description_slogan">
            轟然作響的歪斜世界裡，<br />夏油傑需要一個乾淨明亮的地方。
          </div>
          <div class="about__description_detail">
            在海明威的同名小說中，「乾淨明亮的地方」<br
              v-if="isMobile"
            />近似於維繫尊嚴以求保持站立的意象，<br />
            也暗指戰爭導致世界傾頹、心靈茫然。<br /><br v-if="isMobile" />

            然而對夏油傑來說，<br v-if="isMobile" />
            他的「乾淨」與「明亮」又是什麼呢，<br v-if="isMobile" />
            他所希冀的秩序，<br v-if="!isMobile" />以及<br
              v-if="isMobile"
            />兌現秩序的場所又是什麼呢？<br v-if="isMobile" />
            他需要，他其實不需要，或者他不得不需要？<br /><br />

            五条悟又存在於這個概念的外側還是襯裏、<br v-if="isMobile" />
            是根基還是威脅、是過去還是未來呢？<br />
          </div>
        </div>
        <div class="list">
          <ul class="about__info">
            <li>書名｜一個乾淨明亮的地方</li>
            <li>配對｜夏五無差</li>
            <li>分級｜全年齡（無性描寫）</li>
            <li>規格｜A6 右翻 約4萬字</li>
          </ul>
          <div class="about__group">
            <div>執筆作者群 ｜</div>
            <ul class="about__group_list">
              <li>和樹<a href="https://www.plurk.com/shinsaka">↗</a></li>
              <li>涉江<a href="https://www.plurk.com/Dionysusian">↗</a></li>
              <li>羊眠<a href="https://www.plurk.com/asuka_ss">↗</a></li>
              <li>
                飛嘯<a
                  href="https://archiveofourown.org/users/flighthowl98/works"
                  >↗</a
                >
              </li>
              <li>清茫<a href="https://www.plurk.com/mang_gg0401">↗</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
export default {
  components: {
    SectionTitle,
  },
  props: {
    isMobile: {
      type: Boolean,
      default: true,
    },
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
  display: flex;
  flex-direction: column;
  margin: 32px 48px 0 48px;
  align-items: center;
  @media (min-width: 768px) {
    margin: 32px 42px 0 0;
    align-items: flex-end;
  }
  * {
    text-align: center;
    @media (min-width: 768px) {
      text-align: end;
    }
  }

  &__description {
    &_slogan {
      font-family: Noto Sans;
      font-weight: 200;
      font-size: 14px;
      line-height: 19px;
      color: #fff;
      @media (min-width: 768px) {
        font-weight: 200;
        font-size: 24px;
        line-height: 33px;
        padding-right: 42px;
      }
      @media (min-width: 1200px) {
        font-size: 36px;
        line-height: 49px;
        padding-right: 44px;
      }
    }
    &_detail {
      margin-top: 8px;
      font-family: Noto Sans;
      font-size: 12px;
      line-height: 15px;
      text-align: center;
      color: #2e2e2e;
      @media (min-width: 768px) {
        margin-top: 24px;
        font-size: 14px;
        line-height: 19px;
        text-align: end;
        padding-right: 62px;
      }
      @media (min-width: 1200px) {
        font-size: 18px;
        line-height: 25px;
      }
    }
  }

  .list {
    display: flex;
    flex-direction: column;
  }

  &__info {
    margin-top: 32px;
    font-family: Noto Sans HK;
    font-size: 12px;
    line-height: 17px;
    color: #000000;
    li {
      text-align: start;
    }
    @media (min-width: 768px) {
      font-size: 18px;
      line-height: 26px;
      margin-top: 60px;
    }
    @media (min-width: 1200px) {
      font-size: 28px;
      line-height: 41px;
    }
  }

  &__group {
    margin-top: 12px;
    display: flex;
    font-family: Noto Sans HK;
    font-weight: 900;
    font-size: 14px;
    line-height: 20px;
    color: #000000;
    div {
      margin-right: 4px;
    }
    a {
      color: #000;
    }
    @media (min-width: 768px) {
      font-size: 20px;
      line-height: 29px;
      &_list {
        display: flex;
        li + li {
          margin-left: 20px;
        }
      }
    }
    @media (min-width: 1200px) {
      font-size: 28px;
      line-height: 41px;
    }
  }
}
</style>
