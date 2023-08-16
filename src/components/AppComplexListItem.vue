<template>
  <li class="complex-table__row">
    <div class="complex-table__left">
      <div class="complex-table__col complex-table__col_name">
        {{ complex.name }}
      </div>
      <div class="complex-table__col complex-table__col_count">
        {{ complex.count }}
      </div>
      <div class="complex-table__col complex-table__col_city">
        {{ complex.city }}
      </div>
      <div class="complex-table__col complex-table__col_district">
        {{ complex.district }}
      </div>
      <div class="complex-table__col complex-table__col_period">
        {{ complex.period }}
      </div>
    </div>
    <div class="complex-table__right">
      <div class="complex-table__col complex-table__col_manager">
        {{ complex.manager }}
      </div>
      <div class="complex-table__col complex-table__col_tel">
        <a :href="`tel:${complex.tel}`"></a> {{ complex.tel }}
      </div>
      <div class="complex-table__col complex-table__col_excel"></div>
      <div class="complex-table__col complex-table__col_pdf"></div>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    complex: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style></style>
