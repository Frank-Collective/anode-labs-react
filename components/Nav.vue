<template>
  <nav>
    <div class="inner">
      <div class="logo">
        <a v-if="currentRoute == 'index'" v-scroll-to="'#top'">
          <img src="/images/logo.svg" alt="" />
        </a>
        <nuxt-link v-if="currentRoute != 'index'" to="/">
          <img src="/images/logo.svg" alt="" />
        </nuxt-link>
      </div>
      <div class="nav-links">
        <ul>
          <li>
            <Link :link="{ title: 'Our Values', url: '#future-focused' }" />
          </li>
          <li>
            <Link :link="{ title: 'How It Works', url: '#meet-network' }" />
          </li>
          <li><a href="#">Join Us</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return { currentRoute: null };
  },

  mounted() {
    this.currentRoute = this.$route.name;
  },
  methods: {},
  watch: {
    $route(to, from) {
      this.currentRoute = to.name;
    },
  },
};
</script>

<style lang="scss" scoped>
nav {
  position: relative;
  z-index: 10;
  height: 0px;

  .inner {
    @include gutter(padding-left);
    @include gutter(padding-right);
    @include clamp("padding-top", 26px, 5.21vw, 100px);
    display: flex;
    justify-content: space-between;
    .logo {
      a {
        display: block;
        width: 216px;
        @include clamp("width", 111px, 14vw, 250px);
        cursor: pointer;

        img {
          display: block;
          width: 100%;
          height: auto;
        }
      }
    }

    .nav-links {
      @include breakpoint(small) {
        display: none;
      }

      ul {
        display: flex;
        li {
          margin-left: 2em;
          &:first-of-type {
            margin-left: 0;
          }
        }
      }
      a {
        text-decoration: none;
        color: $white;
        text-transform: uppercase;
        font-family: "Test Söhne Breit";
        cursor: pointer;

        &:hover {
          color: $yellow;
        }
      }
    }
  }
}
</style>
