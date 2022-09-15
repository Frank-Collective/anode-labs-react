<template>
  <footer v-if="data">
    <div class="inner">
      <div class="copy">
        <h3 v-if="data.title" v-html="data.title"></h3>
        <Link v-if="data.ctaLink" :link="data.ctaLink" :classes="'button'" />
      </div>
      <div class="bottom">
        <div class="logo">
          <img v-if="data.logo" :src="data.logo.mediaItemUrl" alt="" />
        </div>
        <div class="nav-links">
          <ul>
            <li v-for="(link, index) in data.links" :key="index">
              <Link :link="link.link" />
            </li>
          </ul>
        </div>
        <div class="dummy-element"></div>
        <div class="socials">
          <ul>
            <li v-for="(link, index) in data.socialMediaLinks" :key="index">
              <a :href="link.url" target="_blank">
                <img :src="link.icon.mediaItemUrl" alt="" />
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import { gql } from "nuxt-graphql-request";
import { image, link } from "~/gql/common";

export default {
  data() {
    return { data: null };
  },
  async fetch() {
    const query = gql`
      query MyQuery {
        globalContent {
          FooterFields {
            footerFields {
              title
              ctaLink {
                ${link}
              }
              logo {
                ${image}
              }
              links {
                link {
                  ${link}
                }
              }
              socialMediaLinks {
                icon {
                  ${image}
                }
                url
              }
            }
          }
        }
      }
    `;
    const data = await this.$graphql.default.request(query);
    this.data = data.globalContent.FooterFields.footerFields;
    //console.log(this.data);
  },
  mounted() {},
};
</script>

<style lang="scss" scoped>
footer {
  position: relative;
  background: linear-gradient(0deg, #06c290 -12.43%, #0c2d24 34.42%);
  padding-top: 5vw;
  padding-bottom: 2vw;

  @include breakpoint(small) {
    padding: 60px 0px;
  }

  .inner {
    @include gutter(padding-left);
    @include gutter(padding-right);
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
    height: 100%;

    .copy {
      width: 50%;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      margin-bottom: 10.2vw;

      @include breakpoint(small) {
        width: 70%;
      }

      h3 {
        font-weight: 100;
        @include clamp("font-size", 34px, 4.17vw, 80px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: capitalize;
        margin-bottom: 0.75em;
      }
    }
    .bottom {
      display: flex;
      justify-content: space-between;
      width: 100%;

      @include breakpoint(small) {
        flex-direction: column;
        margin-top: 100px;
      }

      .logo {
        @include breakpoint(small) {
          order: 2;
        }

        img {
          @include breakpoint(small) {
            width: 30px;
          }
        }
      }

      .nav-links {
        ul {
          display: flex;

          @include breakpoint(small) {
            flex-direction: column;
          }

          li {
            margin-left: 2em;

            &:first-of-type {
              margin-left: 0;
            }

            @include breakpoint(small) {
              margin-left: 0;
              margin-bottom: 30px;
            }
          }
        }
        a {
          text-decoration: none;
          color: $white;
          text-transform: uppercase;
          font-family: "Test Söhne Breit";
          &:hover {
            color: $yellow;
          }
        }
      }
      .dummy-element {
        width: 150px;
      }

      .socials {
        position: fixed;
        bottom: 3vw;
        right: 6.7vw;
        z-index: 100;

        ul {
          display: flex;
          li {
            margin-left: 1em;

            &:first-of-type {
              margin-left: 0;
            }

            svg {
              @include breakpoint(small) {
                width: 30px;
              }
            }
          }
        }
      }
    }
  }
}
</style>
