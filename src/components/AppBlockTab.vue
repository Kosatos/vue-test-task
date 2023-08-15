<template>
  <div class="tab">
    <input type="checkbox" class="tab__input" :id="id" v-model="active" />
    <label class="tab__label" :for="id">{{ name }}</label>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    isActive: {
      type: Boolean,
      required: false,
      default: () => false,
    },
  },
  data() {
    return {
      active: this.isActive,
    }
  },
}
</script>

<style lang="scss">
.tab {
  &__input {
    display: none;
  }
  &__label {
    font-size: 12px;
    font-weight: 500;
    display: flex;
    align-items: center;
    gap: 10px;
    background-color: #fff;
    border: 1px solid #621280;
    border-radius: 10px;
    padding: 12px;
  }
}
</style>
