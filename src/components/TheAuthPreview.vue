<template>
  <div class="auth-preview">
    <span class="auth-preview__name">
      Вы вошли как Администратор EasyLife <br />
      VLADIMIR SIKHVART
    </span>
    <img
      src="../assets/img/logo.png"
      alt="avatar"
      class="auth-preview__avatar"
    />
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.auth-preview {
  display: flex;
  gap: 12px;
  align-items: center;
  &__name {
    text-align: right;
    font-size: 10px;
    font-weight: 600;
    line-height: 1.4em;
  }
  &__avatar {
    width: 42px;
    height: 42px;
    object-fit: contain;
  }
}
</style>
