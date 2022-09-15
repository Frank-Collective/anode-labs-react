<template>
  <div class="inner" v-if="data">
    <div class="copy">
      <h2 :id="data.sectionId" v-if="data.title" v-html="data.title"></h2>
      <ExpandingContent
        v-for="(block, index) in data.contentBlock"
        :key="index"
        :data="{
          callback: display_image,
          index: index,
          image: block.icon,
          title: block.title,
          content: block.copy,
        }"
      />
    </div>
    <div class="images">
      <template v-for="(block, index) in data.contentBlock">
        <div
          :key="index"
          class="dot"
          v-bind:class="{ expanded: current_image_index == index }"
        ></div>
        <div
          :key="`${index}1`"
          class="image"
          v-bind:class="{
            expanded: current_image_index == index,
            last: index == data.contentBlock.length - 1,
          }"
        >
          <img :src="block.image.mediaItemUrl" alt="" />
        </div>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: Object,
  },
  data() {
    return {
      current_image_index: -1,
    };
  },
  mounted() {
    // console.log(this.data);
  },
  methods: {
    display_image: function (index) {
      this.current_image_index = index;
    },
  },
};
</script>

<style lang="scss" scoped>
.inner {
  position: relative;
  display: flex;
  justify-content: space-between;

  @include breakpoint(small) {
    width: 100%;
    @include gutter(padding-left);
    @include gutter(padding-right);
  }

  .copy {
    width: 56.52%;
    flex-shrink: 0;
    @include gutter(padding-left);
    padding-top: 10vw;
    padding-bottom: 10vw;

    @include breakpoint(small) {
      width: 100%;
      padding: 70px 0 50px;
    }

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      letter-spacing: 0.04em;
      margin-bottom: 0.6em;

      @include breakpoint(small) {
        text-align: center;
        margin-bottom: 2.5em;
      }
    }
  }

  .images {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: sticky;
    top: 0;
    height: 100vh;
    @include gutter(margin-right);

    @include breakpoint(small) {
      display: none;
    }

    &:before {
      content: "";
      display: block;
      position: absolute;
      width: 3px;
      height: 100%;
      background-color: $dark_green;
      left: 50%;
      transform: translateX(-50%);
    }

    .dot {
      position: relative;
      flex-shrink: 0;
      width: 2.5vw;
      height: 2.5vw;
      border-radius: 100%;
      background-color: $dark_green;
      transition: 0.5s background-color, 0.5s width, 0.5s height;
      margin: 3vw 0;

      &:first-of-type {
        width: 4.2vw;
        height: 4.2vw;
      }

      &.expanded {
        background-color: $light_green;
        width: 4.2vw;
        height: 4.2vw;
      }
    }

    .image {
      position: relative;
      width: 31.2vw;
      height: 0px;
      overflow: hidden;
      z-index: 1;
      transition: 0.5s height;

      &.expanded {
        height: 29.2vw;
      }

      &.last {
        margin-bottom: 3vw;
      }

      img {
        position: absolute;
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
