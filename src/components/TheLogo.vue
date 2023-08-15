<template>
  <div class="logo">
    <img src="../assets/img/logo.png" alt="logo" class="logo__img" />
    <div class="logo__title logo__text">
      <span>easy life</span>
      <span class="logo__text_big">homes</span>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.logo {
  position: relative;
  img {
  }
  &__title {
    position: absolute;
    top: calc(100% + 5px);
    left: 50%;
    transform: translateX(-50%);
    width: max-content;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &__text {
    color: #621280;
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    &_big {
      font-size: 13px;
    }
  }
}
</style>
