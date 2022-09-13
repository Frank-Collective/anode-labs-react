<template>
  <div class="inner">
    <div class="copy">
      <h2>Meet The <br />React Network</h2>
      <ExpandingContent
        :data="{
          callback: display_image,
          index: 0,
          image: { mediaItemUrl: '/images/icon-bulb.svg' },
          title: 'The Network for<br>Energy Flexibility',
          content:
            '<p>Renewable energy is growing fast. That’s a good thing for our environment and health. However, renewable energy can also be unstable.</p><p>Energy flexibility smooths out the ebbs and flows of renewable energy. React is creating a network of distributed devices to provide this critical flexibility.</p><p>The React Network coordinates thousands of connected energy devices when the grid is under stress and having a difficult time providing reliable service. These small adjustments add up to a massive source of value for energy grids– value that is returned to you.</p>',
        }"
      />
      <ExpandingContent
        :data="{
          callback: display_image,
          index: 1,
          image: { mediaItemUrl: '/images/icon-0101.svg' },
          title: 'Earn React Tokens<br>For Contributing',
          content:
            '<p>Once connected, your energy devices mint React Tokens automatically. React handles the rest.</p><p>On the other side of the network, energy market participants consume React tokens to procure energy flexibility, reducing the total token supply to maintain a healthy market.</p>',
        }"
      />
      <ExpandingContent
        :data="{
          callback: display_image,
          index: 2,
          image: { mediaItemUrl: '/images/icon-people2.svg' },
          title: 'Collective<br>Ownership',
          content:
            '<p>The React Network belongs to its builders. As a community-owned energy platform, individual contributions are rewarded with ownership in the network itself. React tokens represent your personal stake in the grid’s sustainability gains.</p><p>As our community grows, the React Network grows more valuable in its ability to effect meaningful change. Because there’s Power in Numbers</p>',
        }"
      />
    </div>
    <div class="images">
      <div
        class="dot"
        v-bind:class="{ expanded: current_image_index == 0 }"
      ></div>
      <div class="image" v-bind:class="{ expanded: current_image_index == 0 }">
        <img src="/images/section4-image-0.jpg" alt="" />
      </div>
      <div
        class="dot"
        v-bind:class="{ expanded: current_image_index == 1 }"
      ></div>
      <div class="image" v-bind:class="{ expanded: current_image_index == 1 }">
        <img src="/images/section4-image-1.jpg" alt="" />
      </div>
      <div
        class="dot"
        v-bind:class="{ expanded: current_image_index == 2 }"
      ></div>
      <div
        class="image last"
        v-bind:class="{ expanded: current_image_index == 2 }"
      >
        <img src="/images/section4-image-2.jpg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current_image_index: -1,
    };
  },
  methods: {
    display_image: function (index) {
      if (index > this.current_image_index) {
        this.current_image_index = index;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.inner {
  position: relative;
  display: flex;
  justify-content: space-between;

  .copy {
    width: 56.52%;
    flex-shrink: 0;
    @include gutter(padding-left);
    padding-top: 10vw;
    padding-bottom: 10vw;

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      letter-spacing: 0.04em;
      margin-bottom: 0.6em;
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
      width: 47px;
      height: 47px;
      border-radius: 100%;
      background-color: $dark_green;
      transition: 0.5s background-color;
      margin: 3vw 0;

      &:first-of-type {
        width: 80px;
        height: 80px;
      }

      &.expanded {
        background-color: $light_green;
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
