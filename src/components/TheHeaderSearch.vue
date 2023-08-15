<template>
  <div class="header-search">
    <div class="header-search__icon">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 17 17" fill="none">
        <path
          d="M15.5833 15.5834L14.1666 14.1667M8.14579 14.875C9.02948 14.875 9.90451 14.701 10.7209 14.3628C11.5374 14.0246 12.2792 13.529 12.904 12.9041C13.5289 12.2792 14.0246 11.5374 14.3627 10.721C14.7009 9.90457 14.875 9.02954 14.875 8.14585C14.875 7.26217 14.7009 6.38713 14.3627 5.57071C14.0246 4.75429 13.5289 4.01248 12.904 3.38761C12.2792 2.76275 11.5374 2.26709 10.7209 1.92891C9.90451 1.59074 9.02948 1.41669 8.14579 1.41669C6.36111 1.41669 4.64952 2.12565 3.38755 3.38761C2.12559 4.64958 1.41663 6.36117 1.41663 8.14585C1.41663 9.93054 2.12559 11.6421 3.38755 12.9041C4.64952 14.1661 6.36111 14.875 8.14579 14.875V14.875Z"
          stroke-width="1.3"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </div>

    <input
      class="header-search__input"
      type="text"
      placeholder="Название комплекса"
    />
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.header-search {
  position: relative;
  &__icon {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 12px;
    width: 17px;
    height: 17px;
    svg {
      width: 100%;
      height: 100%;
      stroke: #000;
      opacity: 0.5;
    }
  }
  &__input {
    width: 100%;
    padding: 12px 12px 12px 40px;
    font-size: 12px;
    line-height: 1.6em;
    border: none;
    border-radius: 10px;
    background-color: #fff;
    &::placeholder {
      font-size: 10px;
    }
  }
}
</style>
