<template>
  <footer>
    <div class="inner">
      <div class="logo">
        <img src="/images/logo-footer.svg" alt="" />
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  position: relative;

  .inner {
    @include gutter(padding-left);
    @include gutter(padding-right);
  }
}
</style>
