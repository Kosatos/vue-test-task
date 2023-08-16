<template>
  <li class="tab">
    <input
      type="radio"
      class="tab__input"
      :id="id"
      v-model="active"
      :checked="active"
      name="block-content"
      @input="$emit('setActive', id)"
    />
    <label class="tab__label" :for="id">
      <svg viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M9.16667 12.5H14.1667V14.1667H9.16667V12.5ZM7.5 5.83333H5.83333V7.5H7.5V5.83333ZM9.16667 10.8333H14.1667V9.16667H9.16667V10.8333ZM9.16667 7.5H14.1667V5.83333H9.16667V7.5ZM7.5 9.16667H5.83333V10.8333H7.5V9.16667ZM17.5 4.16667V15.8333C17.5 16.75 16.75 17.5 15.8333 17.5H4.16667C3.25 17.5 2.5 16.75 2.5 15.8333V4.16667C2.5 3.25 3.25 2.5 4.16667 2.5H15.8333C16.75 2.5 17.5 3.25 17.5 4.16667ZM15.8333 4.16667H4.16667V15.8333H15.8333V4.16667ZM7.5 12.5H5.83333V14.1667H7.5V12.5Z"
        />
      </svg>
      <span>{{ name }}</span>
    </label>
  </li>
</template>

<script>
export default {
  emits: ['setActive'],
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
    margin-right: 15px;
    font-size: 12px;
    font-weight: 500;
    display: flex;
    align-items: center;
    gap: 10px;
    background-color: #fff;
    border: 1px solid #621280;
    border-radius: 10px;
    padding: 12px;
    transition: margin-right 0.2s ease, border 0.4s ease;
    cursor: pointer;
    svg {
      width: 20px;
      height: 20px;
      fill: #000;
    }
  }
  &__input:checked ~ &__label {
    margin-right: -1px;
    border-right: none;
    border-radius: 10px 0 0 10px;
  }
}
</style>
