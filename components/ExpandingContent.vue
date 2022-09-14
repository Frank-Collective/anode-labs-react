<template>
  <div
    class="expanding-content"
    v-bind:class="[{ expanded: expanded }]"
    ref="ec"
  >
    <div class="inner">
      <div class="title">
        <img :src="data.image.mediaItemUrl" alt="" />
        <h3 v-html="data.title"></h3>
      </div>
      <transition
        v-on:before-enter="beforeEnter"
        v-on:enter="enter"
        v-on:after-enter="afterEnter"
        v-on:before-leave="beforeLeave"
        v-on:leave="leave"
      >
        <div class="content" v-show="expanded" v-html="data.content"></div>
      </transition>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  props: { data: Object },
  data() {
    return {
      scrolltrigger_initiated: false,
      expanded: true,
    };
  },
  mounted() {
    setTimeout(() => {
      this.scrollTriggerInit();
    }, 500);
  },
  methods: {
    scrollTriggerInit() {
      if (!this.scrolltrigger_initiated && process.client) {
        this.scrolltrigger_initiated = true;
        this.add_expanding_content_trigger();
      }
    },
    add_expanding_content_trigger() {
      let el = this.$refs.ec;
      const timeline = gsap.timeline({
        scrollTrigger: {
          trigger: el,
          start: "top center",
          end: "bottom center",
          onEnter: () => {
            // console.log("onEnter");
            this.expanded = true;
            this.data.callback(this.data.index);

            // setTimeout(() => {
            //   ScrollTrigger.refresh();
            // }, 500);
          },
          onEnterBack: () => {
            console.log("onEnterBack");
            this.expanded = true;
            this.data.callback(this.data.index);
          },
          onLeave: () => {
            // console.log("onLeave");
          },
          onLeaveBack: () => {
            // console.log("onLeaveBack");
          },
        },
      });
    },
    toggleContent: function () {
      this.expanded = !this.expanded;
    },
    openContent: function (e, el) {
      if (this.expanded) {
        this.closeContent();
      } else {
        this.expanded = true;
        if (this.data.callback != null) {
          this.data.callback(this.data.index);
        }
      }
    },
    closeContent: function () {
      this.expanded = false;
    },
    beforeEnter: function (el) {
      el.style.height = "0";
    },
    enter: function (el) {
      el.style.height = el.scrollHeight + "px";
    },
    afterEnter: function (el) {
      el.style.height = "auto";
    },
    beforeLeave: function (el) {
      const height = getComputedStyle(el).height;
      el.style.height = height;
      // Force repaint to make sure the
      // animation is triggered correctly.
      getComputedStyle(el).height;
    },
    leave: function (el) {
      el.style.height = 0;
    },
  },
};
</script>

<style lang="scss" scoped>
.expanding-content {
  position: relative;
  border-top: 3px solid $slate;

  &.expanded {
    .inner {
      .content {
        height: auto;
      }
    }
  }

  .inner {
    padding: 3vw 0;

    @include breakpoint(small) {
      padding: 20px 0 40px;
    }

    .title {
      display: flex;
      align-items: center;

      @include breakpoint(small) {
        flex-direction: column;
        align-items: flex-start;
      }

      img {
        transition: 0.15s opacity;
        margin-right: 3vw;

        @include breakpoint(small) {
          width: 55px;
          margin-right: 0;
        }
      }

      h3 {
        font-size: 38px;
        @include clamp("font-size", 34px, 1.98vw, 38px);
        line-height: 120%;
        letter-spacing: -0.01em;
        padding: 1.25em 0;

        @include breakpoint(small) {
          padding: 0.5em 0 1em;
        }
      }
    }

    :deep(.content) {
      position: relative;
      height: 0px;
      overflow: hidden;
      transition: 0.5s;

      p {
        margin-bottom: 1em;
      }
    }
  }
}
</style>
