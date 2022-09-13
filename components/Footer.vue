<template>
  <footer>
    <div class="inner">
      <div class="copy">
        <h3>Help Us Build The Future of Energy</h3>
        <a href="#" class="button">Add me to the waitlist</a>
      </div>
      <div class="logo">
        <img src="/images/logo-footer.svg" alt="" />
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  position: relative;
  background: linear-gradient(0deg, #06c290 -12.43%, #0c2d24 34.42%);
  padding-top: 5vw;
  padding-bottom: 2vw;

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

      h3 {
        font-weight: 100;
        @include clamp("font-size", 34px, 4.17vw, 80px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: capitalize;
        margin-bottom: 0.75em;
      }
    }

    .logo {
    }
  }
}
</style>
