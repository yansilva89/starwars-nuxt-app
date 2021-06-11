<template>
  <div class="cp-wrapper">
    <div class="left">
      <slot name="left" />
    </div>
    <div class="right">
      <slot name="right" />
    </div>
  </div>
</template>

<style lang="scss">
  .cp-wrapper {
    height: 100%;
    display: flex;
    width: 100%;
    overflow: hidden;
    .left, .right {
      height: 100%;
      flex: 1;
    }
  }
</style>
