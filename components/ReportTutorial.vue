<template>
  <div class="report-tutorial">
    <BaseSubtitle
      text="兩種方式，三個步驟"
      class="report-tutorial__base-subtitle"
    />
    <div class="border-steps">
      <div class="title-steps">
        <div class="title-steps-text">協助回報違章工廠</div>
      </div>
      <div class="steps">
        <div v-for="step in steps" :key="step.num" class="step">
          <div class="title">
            <div class="num">{{ step.num }}</div>
            <p>{{ step.title }}</p>
          </div>
          <picture>
            <source
              type="image/webp"
              :srcset="require(`~/assets/imgs/${step.imgName}.webp`)"
            />
            <img :src="require(`~/assets/imgs/${step.imgName}.png`)" alt="" />
          </picture>
        </div>
      </div>

      <div class="button-border">
        <a
          href="https://bit.ly/39WGOhR"
          target="_blank"
          rel="noopener"
          @click="$ga.event('introduction', 'go2report', 'intro')"
          >新增可疑工廠</a
        >
      </div>
    </div>

    <div class="action">
      <picture>
        <source type="image/webp" srcset="~/assets/imgs/logo.webp" />
        <img
          class="logo"
          width="151"
          height="151"
          src="~/assets/imgs/logo.png"
          alt=""
        />
      </picture>

      <div class="text">
        <p class="slogan">匿名、快速、方便</p>
        <p class="description">
          傳統的檢舉需要留下個人資料，且程序往往複雜。本系統協助你快速、匿名檢舉。簡單三步驟回報，還不用擔心被找碴。
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import BaseSubtitle from '~/components/BaseSubtitle.vue'

export default {
  name: 'ReportTutorial',

  components: {
    BaseSubtitle,
  },

  setup() {
    return {
      steps: [
        {
          num: 1,
          title: '拍照',
          imgName: 'factory-photo',
        },
        {
          num: 2,
          title: '標記地點+上傳',
          imgName: 'upload',
        },
        {
          num: 3,
          title: '地球公民基金會幫你檢舉',
          imgName: 'report-help',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.report-tutorial {
  padding: 40px 24px;
  text-align: center;
  background-color: #fbfdf0;
  @include media-breakpoint-up(lg) {
    padding: 60px 40px 80px 40px;
  }

  &__base-subtitle {
    margin-bottom: 32px;
    @include media-breakpoint-up(lg) {
      margin-bottom: 72px;
    }
  }
}

.border-steps {
  border: 5px solid #eaf3bf;
  box-sizing: border-box;
  border-radius: 5px;
  margin-bottom: 83px;

  @include media-breakpoint-up(xl) {
    margin-left: 146px;
    margin-right: 146px;
  }
}

.button-border {
  transform: translateY(27px);
}

.title-steps {
  @include media-breakpoint-up(lg) {
    display: flex;
    max-width: 1127px;
    margin-right: auto;
    margin-left: auto;
  }
  @media only screen and (min-width: 1600px) {
    max-width: 1151px;
  }
}

.title-steps-text {
  //styleName: LandingPage / heading / M;
  display: inline-block;
  background: #fbfdf0;
  font-size: 30px;
  font-style: normal;
  font-weight: 700;
  line-height: 44px;
  letter-spacing: 0.8550000190734863px;
  text-align: center;
  transform: translateY(-23px);
  padding: 1px 12px;
  @include media-breakpoint-up(lg) {
    margin-left: 44px;
  }

  @media only screen and (min-width: 1550px) {
    margin-left: unset;
  }
}

.steps {
  @include media-breakpoint-up(lg) {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    max-width: 1127px;
    margin: 0 auto 0 auto;
    padding-left: 56px;
    padding-right: 56px;
    // margin-left: 56px;
    // margin-right: 56px;
  }
}

.step {
  font-weight: 700;
  margin-bottom: 40px;
  @include media-breakpoint-up(lg) {
    margin-bottom: 0;
    width: calc(100% / 3 - 42.67px);
  }

  img {
    width: 100%;
    max-width: 333px;
    margin: 0 auto;
  }

  p {
    font-size: 22px;
    color: #4a5613;
  }
}

.title {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 8px;
  @include media-breakpoint-up(lg) {
    margin-bottom: 24px;
    justify-content: flex-start;
  }
}

.num {
  background-color: #eaf3bf;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  font-weight: 700;
  font-size: 20px;
  line-height: 1.15;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 20px;
  flex-shrink: 0;
}

.action {
  @include media-breakpoint-up(lg) {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}

.logo {
  width: 151px;
  margin: 0 auto 24px auto;
  @include media-breakpoint-up(lg) {
    margin: 0 32px 0 0;
  }
}

.text {
  @include media-breakpoint-up(lg) {
    margin-right: 36px;
  }
}

.slogan {
  font-weight: 700;
  font-size: 28px;
  margin-bottom: 8px;
  @include media-breakpoint-up(lg) {
    text-align: left;
  }
}

.description {
  font-size: 23px;
  text-align: left;
  max-width: 333px;
  margin: 0 auto 32px auto;
  @include media-breakpoint-up(lg) {
    margin: 0 auto;
    max-width: 355px;
    font-size: 17px;
  }
}

a {
  background-color: #697f01;
  border-radius: 34px;
  color: #fff;
  font-weight: 700;
  font-size: 20px;
  padding: 12px 28px;
  display: inline-block;
  transition: background-color 0.2s;
  @include media-breakpoint-up(lg) {
    flex-shrink: 0;
  }

  &:hover {
    background-color: #4a5613;
  }
}
</style>
