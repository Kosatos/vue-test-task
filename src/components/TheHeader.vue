<template>
  <header class="header">
    <div class="container header__container">
      <div class="header__left">
        <TheLogo />
        <TheHeaderSearch class="header__search" />
      </div>

      <div class="header__block-title">Список Комплексов</div>

      <div class="header__right">
        <TheAuthPreview />
      </div>

      <TheLangSwitcher class="header__lang" />
    </div>
  </header>
</template>

<script>
import TheLogo from './TheLogo.vue'
import TheHeaderSearch from './TheHeaderSearch.vue'
import TheAuthPreview from './TheAuthPreview.vue'
import TheLangSwitcher from './TheLangSwitcher.vue'
export default {
  components: {
    TheLogo,
    TheHeaderSearch,
    TheAuthPreview,
    TheLangSwitcher,
  },
}
</script>

<style lang="scss">
.header {
  padding: 20px 0;
  &__container {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__left {
    display: flex;
    align-items: flex-start;
    gap: 43px;
  }
  &__search {
    width: 250px;
  }
  &__block-title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 15px;
    font-weight: 600;
  }
  &__lang {
    position: absolute;
    bottom: -100px;
    left: 15px;
  }
}
</style>
