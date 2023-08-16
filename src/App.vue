<template>
  <TheHeader />
  <main class="main">
    <div class="container main__container">
      <div class="main__content">
        <ul class="main__tabs">
          <AppBlockTab
            v-for="tab in tabs"
            :key="tab.id"
            class="main__tab"
            :id="tab.id"
            :name="tab.name"
            :isActive="tab.isActive"
            @setActive="changeActive"
          />
        </ul>
        <div
          class="main__block"
          :class="{ 'main__block_not-round': isFirstBlockActive }"
        >
          <AppComplexList
            v-show="tabs.find((tab) => tab.id === 'rc-list').isActive"
          />
          <AppAddComplexForm
            v-show="tabs.find((tab) => tab.id === 'rc-add').isActive"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import AppBlockTab from './components/AppBlockTab.vue'
import AppComplexList from './components/AppComplexList.vue'
import AppAddComplexForm from './components/AppAddComplexForm.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    AppBlockTab,
    AppComplexList,
    AppAddComplexForm,
  },
  data() {
    return {
      tabs: [
        { id: 'rc-list', name: 'Список ЖК', isActive: true },
        { id: 'rc-add', name: 'Добавить ЖК', isActive: false },
      ],
    }
  },

  computed: {
    isFirstBlockActive() {
      return this.tabs[0].isActive
    },
  },
  methods: {
    changeActive(id) {
      console.log(this.tabs)
      this.tabs.forEach((tab) => (tab.isActive = tab.id === id))
    },
  },
}
</script>

<style lang="scss">
.main {
  &__container {
  }
  &__content {
    display: flex;
    justify-content: space-between;
    margin-left: 93px;
  }
  &__tabs {
    flex: 1;
  }
  &__tab {
    position: relative;
    width: 100%;
    &:not(:last-child) {
      margin-bottom: 10px;
    }
  }
  &__block {
    max-width: 898px;
    width: 100%;
    // height: calc(100vh - 100px);
    background-color: #fff;
    border: 1px solid #621280;
    border-radius: 10px;
    padding: 14px;
    transition: border-radius 0.4s ease;
    &_not-round {
      border-radius: 0 10px 10px 10px;
    }
  }
}
</style>
