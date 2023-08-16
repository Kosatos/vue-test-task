<template>
  <table class="complex-table">
    <thead class="complex-table__header">
      <tr class="complex-table__row">
        <th class="complex-table__column">Название</th>
        <th class="complex-table__column">Кол-во квартир</th>
        <th class="complex-table__column">Город</th>
        <th class="complex-table__column">Район</th>
        <th class="complex-table__column">Период обслуживания</th>
        <th class="complex-table__column">Менеджер</th>
        <th class="complex-table__column">Номер Телефона</th>
      </tr>
    </thead>
  </table>
</template>

<script>
export default {}
</script>

<style lang="scss">
table {
  min-width: 100vw;
  width: auto;
  flex: 1;
  display: grid;
  border-collapse: collapse;
  /* These are just initial values which are overriden using JavaScript when a column is resized */
  grid-template-columns:
    minmax(150px, 1fr)
    minmax(150px, 1.67fr)
    minmax(150px, 1.67fr)
    minmax(150px, 1.67fr)
    minmax(150px, 3.33fr)
    minmax(150px, 1.67fr)
    minmax(150px, 3.33fr)
    minmax(150px, 1.67fr);
}

thead,
tbody,
tr {
  display: contents;
}

th,
td {
  padding: 15px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

th {
  position: sticky;
  top: 0;
  background: #6c7ae0;
  text-align: left;
  font-weight: normal;
  font-size: 1.1rem;
  color: white;
}

th:last-child {
  border: 0;
}

.resize-handle {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  background: black;
  opacity: 0;
  width: 3px;
  cursor: col-resize;
}
td {
  padding-top: 10px;
  padding-bottom: 10px;
  color: #808080;
}

tr:nth-child(even) td {
  background: #f8f6ff;
}
</style>
