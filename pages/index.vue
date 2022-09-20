<template>
  <div id="top" v-if="page">
    <div class="section-1">
      <div class="bg-image">
        <img class="background desktop" src="/images/section-1-bg.jpg" alt="" />
        <img
          class="background mobile"
          src="/images/section-1-bg-mobile.png"
          alt=""
        />
        <img
          class="grid desktop"
          src="/images/section-1-grid-bg.svg"
          alt=""
          data-st-slide_down_enter
        />
        <img
          class="grid mobile"
          src="/images/section-1-grid-bg-mobile.svg"
          alt=""
        />
      </div>
      <div class="inner" :id="page.hero.sectionId">
        <div class="copy" data-st-slide_up_enter>
          <h1 v-if="page.hero.title" v-html="page.hero.title"></h1>
          <div v-if="page.hero.copy" v-html="page.hero.copy"></div>
          <div class="ctas">
            <Link
              v-if="page.hero.link1"
              :classes="'button'"
              :link="page.hero.link1"
            />
            <Link
              v-if="page.hero.link2"
              :classes="'link'"
              :link="page.hero.link2"
            />
          </div>
        </div>
        <div class="image">
          <model-viewer
            id="hero3d"
            camera-controls
            auto-rotate
            disable-zoom
            interaction-prompt="none"
            auto-rotate-delay="0"
            src="/Earth2.glb"
            alt="Earth at night"
          >
            <div class="poster" slot="poster"></div>
            <div class="progress-bar" slot="progress-bar"></div>
          </model-viewer>
          <div class="ornament">
            <svg
              width="123"
              height="122"
              viewBox="0 0 123 122"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <circle cx="61.4996" cy="7.89412" r="7.89412" fill="#06C290" />
              <circle cx="61.4996" cy="32.2943" r="7.89412" fill="#06C290" />
              <circle cx="8.39412" cy="61.0001" r="7.89412" fill="#06C290" />
              <ellipse
                cx="34.947"
                cy="61.0001"
                rx="7.17647"
                ry="7.89412"
                fill="#06C290"
              />
              <circle cx="61.4996" cy="61.0001" r="7.89412" fill="#F8FF31" />
              <ellipse
                cx="88.0524"
                cy="61.0001"
                rx="7.17647"
                ry="7.89412"
                fill="#F8FF31"
              />
              <circle cx="114.605" cy="61.0001" r="7.89412" fill="#F8FF31" />
              <ellipse
                cx="61.4996"
                cy="88.9882"
                rx="7.89412"
                ry="7.17647"
                fill="#F8FF31"
              />
              <circle cx="61.4996" cy="114.106" r="7.89412" fill="#F8FF31" />
            </svg>
          </div>
          <div class="parens">
            <svg
              width="816"
              height="229"
              viewBox="0 0 816 229"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M30.0018 229H47.2028C30.4018 202.739 17.201 161.508 17.201 115.813C17.201 70.1181 30.4018 26.2615 47.2028 0H30.2018C12.4007 25.4736 0 68.0172 0 115.813C0 163.872 12.2007 203.789 30.0018 229Z"
                fill="#F8FF31"
              />
              <path
                d="M768.597 229H785.798C803.599 203.789 816 163.872 816 115.813C816 68.0172 803.399 25.4736 785.598 0H768.597C785.398 26.2615 798.799 70.1181 798.799 115.813C798.799 161.508 785.398 202.739 768.597 229Z"
                fill="#F8FF31"
              />
            </svg>
          </div>
          <!-- <img src="/images/section-1-image.png" alt="" /> -->
        </div>
      </div>
      <div :id="page.logoSoup.sectionId" class="inner2" data-st-slide_up_enter>
        <h2 v-if="page.logoSoup.title" v-html="page.logoSoup.title"></h2>
        <ul class="large">
          <li
            v-for="(logo, index) in page.logoSoup.logos.slice(0, 2)"
            :key="index"
          >
            <a :href="logo.url" target="_blank">
              <img v-if="logo.image" :src="logo.image.mediaItemUrl" alt="" />
              <img
                class="hover"
                v-if="logo.imageActive"
                :src="logo.imageActive.mediaItemUrl"
                alt=""
              />
            </a>
          </li>
        </ul>
        <ul class="small">
          <template v-for="(logo, index) in page.logoSoup.logos">
            <li :key="index" v-if="index > 1">
              <a :href="logo.url" target="_blank">
                <img v-if="logo.image" :src="logo.image.mediaItemUrl" alt="" />
                <img
                  class="hover"
                  v-if="logo.imageActive"
                  :src="logo.imageActive.mediaItemUrl"
                  alt=""
                />
              </a>
            </li>
          </template>
        </ul>
      </div>
    </div>
    <div class="section-2">
      <div class="bg-image">
        <img
          src="/images/section-2-grid-bg.svg"
          alt=""
          data-st-slide_down_enter
        />
      </div>
      <div class="inner" :id="page.infoSection1.sectionId">
        <div class="image">
          <FadeImage
            v-if="page.infoSection1.image"
            :srcset="page.infoSection1.image.srcSet"
            :sizes="page.infoSection1.image.sizes"
            :src="page.infoSection1.image.mediaItemUrl"
            :alt="page.infoSection1.image.altText"
            :width="page.infoSection1.image.mediaDetails.width"
            :height="page.infoSection1.image.mediaDetails.height"
          />
        </div>
        <div class="copy" data-st-slide_up_enter>
          <h3
            v-if="page.infoSection1.title"
            v-html="page.infoSection1.title"
          ></h3>
          <div
            v-if="page.infoSection1.copy"
            v-html="page.infoSection1.copy"
          ></div>
        </div>
      </div>
    </div>
    <div class="section-3">
      <div class="bg-image">
        <img class="background" src="/images/section-3-bg.jpg" alt="" />
        <img
          class="grid"
          src="/images/section-3-grid-bg.svg"
          alt=""
          data-st-slide_down_enter
        />
      </div>
      <div :id="page.infoCards.sectionId" class="inner" data-st-slide_up_enter>
        <h2 v-if="page.infoCards.title" v-html="page.infoCards.title"></h2>
        <ul>
          <li v-for="(card, index) in page.infoCards.cards" :key="index">
            <img :src="card.icon.mediaItemUrl" alt="" />
            <h3>{{ card.title }}</h3>
            <p>{{ card.text }}</p>
          </li>
        </ul>
      </div>
      <div :id="page.infoSection2.sectionId" class="inner2">
        <div class="copy" data-st-slide_up_enter>
          <h3
            v-if="page.infoSection2.title"
            v-html="page.infoSection2.title"
          ></h3>
          <div
            v-if="page.infoSection2.copy"
            v-html="page.infoSection2.copy"
          ></div>
        </div>
        <div class="image" data-st-slide_up_enter>
          <FadeImage
            v-if="page.infoSection2.image"
            :srcset="page.infoSection2.image.srcSet"
            :sizes="page.infoSection2.image.sizes"
            :src="page.infoSection2.image.mediaItemUrl"
            :alt="page.infoSection2.image.altText"
            :width="page.infoSection2.image.mediaDetails.width"
            :height="page.infoSection2.image.mediaDetails.height"
          />
        </div>
      </div>
    </div>
    <div class="section-4">
      <Section4 :data="page.reactNetwork" />
    </div>
  </div>
</template>

<script>
import meta from "~/plugins/meta.js";
import { gql } from "nuxt-graphql-request";
import { basics, image, featured_image, link, seo_fields } from "~/gql/common";
import scrollTriggerHub from "~/mixins/ScrollTriggerHub";

const gql_content = `
  ${basics}
  ${seo_fields}
  HomePageFields {
    hero {
      sectionId
      title
      copy
      link1 {
        ${link}
      }
      link2 {
        ${link}
      }
    }
    logoSoup {
      sectionId
      title
      logos {
        image {
          ${image}
        }
        imageActive {
          ${image}
        }
        url
      }
    }
    infoSection1 {
      sectionId
      title
      copy
      image {
        ${image}
      }
    }
    infoCards {
      sectionId
      title
      cards {
        icon {
          ${image}
        }
        title
        text
      }
    }
    infoSection2 {
      sectionId
      title
      copy
      image {
        ${image}
      }
    }
    reactNetwork {
      sectionId
      title
      contentBlock {
        icon {
          ${image}
        }
        title
        copy
        image {
          ${image}
        }
      }
    }
  }
`;

export default {
  mixins: [scrollTriggerHub],
  async asyncData({ $graphql, route }) {
    const query = gql`
      query MyQuery {
        page(id: "home", idType: URI, asPreview: true) {
          ${gql_content}
          isPreview
          preview {
            node {
              ${gql_content}
            }
          }  
        }
      }
    `;
    let { page } = await $graphql.default.request(query);
    page = page.HomePageFields;

    if (route.query && route.query.preview && page.preview) {
      page = page.preview.node;
    }

    return { page };
  },
  methods: {
    make_id(str) {
      str = str.replace(/[^\w\s]|_/g, "");
      return str.replace(/\s/g, "-");
    },
  },
  head() {
    if (this.page && this.page.SeoFields) {
      console.log(this.page.SeoFields);

      return {
        title: this.page.SeoFields.seoTitle
          ? this.page.SeoFields.seoTitle
          : this.page.title,
        meta: meta(this.page.SeoFields),
      };
    }
  },
};
</script>

<style lang="scss" scoped>
.poster,
.progress-bar {
  display: none;
}

.section-1 {
  position: relative;
  padding-top: 13vw;
  padding-bottom: 12.7vw;
  @include gutter(padding-left);
  @include gutter(padding-right);
  overflow: hidden;

  @include breakpoint(small) {
    padding-top: 0;
    padding-bottom: 30px;
  }

  .bg-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;

    img {
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: auto;

      &.desktop {
        @include breakpoint(small) {
          display: none;
        }
      }

      &.mobile {
        display: none;

        @include breakpoint(small) {
          display: block;
        }
      }
    }

    img.background {
      object-fit: cover;
      height: 100%;

      @include breakpoint(small) {
        z-index: 1;
      }
    }

    img.grid {
      @include breakpoint(small) {
        top: -2.5%;
      }
    }
  }

  .inner {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;

    @include breakpoint(small) {
      flex-direction: column;
      padding: 90px 0 0 0;
    }

    .copy {
      @include breakpoint(small) {
        order: 2;
        margin-top: -2.4em;
        z-index: 1000;
      }

      :deep(h1) {
        color: $yellow;
        @include clamp("font-size", 45px, 3.2vw, 60px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: uppercase;
        margin-bottom: 1em;

        @include breakpoint(small) {
          font-weight: normal;
          margin-bottom: 0.2em;
        }
      }

      :deep(p) {
        width: 80%;
        min-width: 380px;
        margin-bottom: 2em;

        @include breakpoint(small) {
          width: 70%;
          margin-bottom: 1.5em;
        }
      }

      .ctas {
        display: flex;
        align-items: center;
      }
    }

    .image {
      width: 55%;
      flex-shrink: 0;
      position: relative;

      @include breakpoint(small) {
        width: 100%;
      }

      #hero3d {
        width: 80%;
        min-height: 500px;
        display: block;
        margin-left: 10%;
        position: relative;
        z-index: 100;

        @include breakpoint(small) {
          min-height: 270px;
          margin-left: 7%;
        }
      }

      .ornament {
        position: absolute;
        top: -5%;
        right: -5%;
        width: 20%;
        z-index: 1;

        @include breakpoint(small) {
          top: -9%;
          right: -2%;
          width: 12%;
        }

        svg {
          width: 100%;
        }
      }

      .parens {
        position: absolute;
        top: 27%;
        left: 0;
        width: 100%;
        z-index: 1;

        @include breakpoint(small) {
          top: 7%;
          width: 94%;
        }

        svg {
          width: 100%;
        }
      }

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }
  }

  .inner2 {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;
    padding-top: 11vw;

    @include breakpoint(small) {
      z-index: 1;
      padding-top: 150px;
    }

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      text-align: center;
      letter-spacing: 0.04em;
      color: $dark_green;
      margin-bottom: 2.5em;

      @include breakpoint(small) {
        margin-bottom: 2em;
      }
    }

    ul {
      list-style: none;
      padding: 0;
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      width: 100%;

      @include breakpoint(small) {
        flex-direction: column;
      }

      &.large {
        li {
          width: 21.4vw;

          @include breakpoint(small) {
            width: 70%;
            margin-bottom: 50px;
          }
        }
      }

      &.small {
        justify-content: space-between;

        li {
          width: 13vw;

          @include breakpoint(small) {
            width: 70%;
            margin-bottom: 50px;
          }

          a {
            img {
              width: 90%;
            }
          }
        }
      }

      li {
        flex-shrink: 0;
        margin-bottom: 5vw;

        @include breakpoint(small) {
          margin-bottom: 0px;
        }

        a {
          position: relative;
          display: flex;
          justify-content: center;

          &:hover {
            img {
              opacity: 0;
            }

            img.hover {
              opacity: 1;
            }
          }

          img {
            display: block;
            width: 100%;
            height: auto;

            &.hover {
              position: absolute;
              top: 0;
              left: 50%;
              transform: translateX(-50%);
              opacity: 0;
              transition: 0.15s opacity;
            }
          }
        }
      }
    }
  }
}

.section-2 {
  position: relative;
  z-index: 1;
  background-color: $dark_green;
  display: flex;
  align-items: center;
  overflow: hidden;

  .bg-image {
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    @include breakpoint(small) {
      display: none;
    }

    img {
      display: block;
      width: 100%;
      height: auto;
    }
  }

  .inner {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: space-between;
    @include gutter(padding-left);
    @include gutter(padding-right);
    margin-top: -10vw;

    @include breakpoint(small) {
      position: relative;
      flex-direction: column;
      padding: 0;
      margin-top: 0;
      padding-bottom: 100px;
    }

    .image {
      position: relative;
      width: 48%;
      flex-shrink: 0;
      padding: 2.55vw;

      @include breakpoint(small) {
        width: 100%;
        height: 79vw;
        overflow: hidden;
        padding: 0;
      }

      img {
        display: block;
        width: 100%;
        height: auto;

        @include breakpoint(small) {
          position: absolute;
          height: 100%;
          object-fit: cover;
        }
      }
    }

    .copy {
      width: 48%;
      flex-shrink: 0;
      padding: 0 2.2vw;

      @include breakpoint(small) {
        padding-top: 40px;
        width: 100%;
        @include gutter(padding-left);
        @include gutter(padding-right);
      }

      :deep(h3) {
        font-weight: 400;
        @include clamp("font-size", 34px, 3.13vw, 60px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: capitalize;
        margin-bottom: 1em;

        span {
          color: $yellow;
        }
      }
    }
  }
}

.section-3 {
  position: relative;
  padding-top: 11.5vw;
  padding-bottom: 12.7vw;
  @include gutter(padding-left);
  @include gutter(padding-right);
  overflow: hidden;

  @include breakpoint(small) {
    padding-top: 90px;
    padding-bottom: 90px;
  }

  .bg-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;

    img {
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: auto;
    }

    img.background {
      object-fit: cover;
      height: 100%;
    }

    img.grid {
      @include breakpoint(small) {
        display: none;
      }
    }
  }

  .inner {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 5vw;
    padding-right: 6.5vw;

    @include breakpoint(small) {
      padding: 0;
    }

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      text-align: center;
      letter-spacing: 0.04em;
      color: $dark_green;
      margin-bottom: 2em;

      @include breakpoint(small) {
        margin-bottom: 1.5em;
      }
    }

    ul {
      display: flex;
      justify-content: space-between;
      list-style: none;
      padding: 0;

      @include breakpoint(small) {
        flex-direction: column;
      }

      li {
        width: calc(33.3333% - 1.5vw);
        background-color: $dark_green;
        border-radius: 20px;
        box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.25);
        padding: 4vw 2vw;

        @include breakpoint(small) {
          width: 100%;
          margin-bottom: 25px;
          padding: 60px 35px;
        }

        img {
          display: block;
          @include clamp("width", 56px, 3.65vw, 70px);
          height: auto;
          margin-bottom: 2vw;

          @include breakpoint(small) {
            margin-bottom: 20px;
          }
        }

        h3 {
          font-weight: 400;
          @include clamp("font-size", 32px, 2.35vw, 45px);
          line-height: 120%;
          padding-bottom: 0.5em;
          margin-bottom: 0.75em;
          border-bottom: 3px solid $yellow;

          @include breakpoint(small) {
            padding-bottom: 1em;
            margin-bottom: 0.5em;
          }
        }

        p {
          @include breakpoint(small) {
            font-size: 22px;
            line-height: 110%;
          }
        }
      }
    }
  }

  .inner2 {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 26vw;

    @include breakpoint(small) {
      flex-direction: column;
      padding-top: 50px;
    }

    .copy {
      width: 40%;
      flex-shrink: 0;
      padding: 0 0;

      @include breakpoint(small) {
        width: 100%;
        order: 2;
      }

      :deep(h3) {
        font-weight: 400;
        @include clamp("font-size", 34px, 3.13vw, 60px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: capitalize;
        margin-bottom: 1em;

        @include breakpoint(small) {
          width: 80%;
        }

        span {
          color: $yellow;
        }
      }
    }

    .image {
      position: relative;
      width: 48%;
      flex-shrink: 0;
      padding: 0 0 0 1.3vw;

      @include breakpoint(small) {
        width: 100%;
        @include neg-gutter(left);
        width: calc(100% + 60px);
        height: 79vw;
        padding: 0;
        margin-bottom: 70px;
        overflow: hidden;
      }

      img {
        display: block;
        width: 100%;
        height: auto;

        @include breakpoint(small) {
          position: absolute;
          height: 100%;
          object-fit: cover;
        }
      }
    }
  }
}

.section-4 {
  position: relative;
  background-color: $yellow;
  color: $slate;
}
</style>
