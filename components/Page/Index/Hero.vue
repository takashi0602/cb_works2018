<template>
  <section class="p-hero">
    <h2 class="p-hero__title">chatboxにできること</h2>
    <div class="p-hero__wrap">
      <div class="p-hero__backgound">
        <div class="p-hero__backgoundFilter"></div>
      </div>
      <div class="p-hero__contents">
        <div class="p-hero__catchCopy">
          <h3 class="p-hero__catchCopyMain">「Webのこれからを<br>「伝える」「語り合う」</h3>
          <span class="p-hero__catchCopySub">作るだけじゃなく、伝えることで見えてくる</span>
        </div>
        <div class="p-hero__lists">
          <hero-list :item="item" :index="index" v-for="(item,index) in listItems"></hero-list>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  import HeroList from './Hero/List.vue'
  export default {
    data () {
      return {
        listItems: [
          {
            title: 'Web制作',
            heading: '企画から制作まで',
            text: 'コーポレートやキャンペーンなどWebサイト制作の多様なニーズに対し、デザインから制作・運用までニーズに合ったトータルサポートで親身に対応させていただきます。',
            number: 'num01',
            thumbnail: '/images/serviceThumb_create.jpg',
            id: 'web'
          },
          {
            title: 'システム開発',
            heading: '高品質・低コスト',
            text: '業務フローの改善から、複雑な要件定義のサポートまで、制作フローの問題を解決します。多くの経験とノウハウで客様にベストなシステム開発を提供します。',
            number: 'num02',
            thumbnail: '/images/serviceThumb_system.jpg',
            id: 'system'
          },
          {
            title: '技術顧問',
            heading: '制作現場の技術力向上をサポート',
            text: '現場のニーズに応じたカリキュラム設計、プロジェクト管理や現場の相談役として技術指導します。',
            number: 'num03',
            thumbnail: '/images/serviceThumb_support.jpg',
            id: 'advise'
          },
          {
            title: 'イベント',
            heading: '職場がスクールに',
            text: '現場の業務ニーズに合わせた柔軟なカリキュラム構成で、スクールを随時開催。最新技術や勉強会の開催で持続的な成長力をもたらします。',
            number: 'num04',
            thumbnail: '/images/serviceThumb_event.jpg',
            id: 'event'
          }
        ]
      }
    },
    components: {
      HeroList
    }
  }
</script>
<style lang="scss" scoped>
  @import "~assets/scss/layout/_layout.scss";
  @import "~assets/scss/object/component/_container.scss";
  .p-hero {
    &__title {
      margin-bottom: 2.5rem;
      color: #C3504F;
      text-align: center;
      font-size: 2rem;
      font-weight: bold;
      letter-spacing: 4px;
      @include desktop {
        margin-bottom: 3.5rem;
        font-size: 2.7rem;
        letter-spacing: 6px;
      }
    }

    &__wrap {
      background-color: #C3504F;
      min-height: 760px;
      position: relative;
    }
    &__backgound  {
      display: none;

      @include desktop {
        display: block;
        height: 450px;
        background: url('/images/hero_background.jpg') no-repeat ;
        background-position: center;
        background-size: cover;
      }
    }
    &__backgoundFilter  {
      height: 100%;
      background-color: rgba(195,80,79,.6);
    }
    &__contents {
      @include c-container;
      padding-top: 30px;
      display: block;
      position: static;

      @include desktop {
        padding-top: 0;
        position: absolute;
        left: 50%;
        top: 70px;
        transform: translateX(-50%);
        z-index: 1000;
      }
    }
    &__catchCopy {
      margin-bottom: 55px;
      text-align: center;
      color: #fff;
      @include desktop {
        margin-bottom: 80px;
      }
    }
    &__catchCopyMain {
      display: block;
      margin-bottom: 10px;
      text-align: center;
      font-size: 2.2rem;
      font-weight: bold;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.4);
      color: inherit;
      line-height: 1.8;
      letter-spacing: 6px;
      @include desktop {
        font-size: 3rem;
        margin-bottom: 30px;
      }
    }
    &__catchCopySub {
      display: inline-block;
      font-size: 1.6rem;
      color: inherit;
      @include desktop {
        font-size: 2rem;
      }
    }
    &__lists {
      display: flex;
      justify-content: space-between;
      flex-wrap:wrap;
      @include desktop {
        flex-wrap: nowrap;
      }
    }

  }
</style>
