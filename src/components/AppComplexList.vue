<template>
  <div class="complex-table">
    <div class="complex-table__row complex-table__row_header">
      <div class="complex-table__left">
        <div class="complex-table__col complex-table__col_name">
          Название
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 10 10"
            fill="none"
          >
            <path
              d="M9.16671 9.16668L8.33337 8.33334M4.79171 8.75001C5.31152 8.75001 5.82625 8.64762 6.3065 8.4487C6.78674 8.24977 7.22311 7.95821 7.59067 7.59064C7.95824 7.22308 8.24981 6.78671 8.44873 6.30647C8.64766 5.82622 8.75004 5.31149 8.75004 4.79168C8.75004 4.27186 8.64766 3.75714 8.44873 3.27689C8.24981 2.79664 7.95824 2.36028 7.59067 1.99271C7.22311 1.62515 6.78674 1.33358 6.3065 1.13465C5.82625 0.935729 5.31152 0.833343 4.79171 0.833344C3.74189 0.833344 2.73507 1.25038 1.99274 1.99271C1.25041 2.73504 0.833374 3.74186 0.833374 4.79168C0.833374 5.84149 1.25041 6.84831 1.99274 7.59064C2.73507 8.33297 3.74189 8.75001 4.79171 8.75001V8.75001Z"
              stroke="black"
              stroke-width="1.3"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </div>
        <div class="complex-table__col complex-table__col_count">
          Кол-во квартир
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="10"
            height="10"
            viewBox="0 0 10 10"
            fill="none"
          >
            <g opacity="0.5">
              <path
                d="M1.25 2.91667H8.75M2.5 5.00001H7.5M4.16667 7.08334H5.83333"
                stroke="black"
                stroke-linecap="round"
              />
            </g>
          </svg>
        </div>
        <div class="complex-table__col complex-table__col_city">Город</div>
        <div class="complex-table__col complex-table__col_district">Район</div>
        <div class="complex-table__col complex-table__col_period">
          Период обслуживания
        </div>
      </div>
      <div class="complex-table__right">
        <div class="complex-table__col complex-table__col_manager">
          Менеджер
        </div>
        <div class="complex-table__col complex-table__col_tel">
          Номер Телефона
        </div>
        <div class="complex-table__col complex-table__col_excel"></div>
        <div class="complex-table__col complex-table__col_pdf"></div>
      </div>
    </div>
    <ul class="complex-table__list">
      <AppComplexListItem
        v-for="(complex, idx) in complexes"
        :key="idx"
        :complex="complex"
      />
    </ul>
  </div>
</template>

<script>
import AppComplexListItem from './AppComplexListItem.vue'
export default {
  components: {
    AppComplexListItem,
  },
  data() {
    return {
      complexes: [
        {
          name: 'SEA PEARL GARDEN',
          count: 52,
          city: 'Alanya',
          district: 'Oba',
          period: '01/01/2022',
          manager: 'Robert Bocsh',
          tel: '+7  916 555 42 33',
        },
        {
          name: 'GOLDCITY AURA 3',
          count: 64,
          city: 'Mahmutlar',
          district: 'Oba',
          period: '12/02/2023',
          manager: 'Selena Dion',
          tel: '+90 535 111 22 33',
        },
        {
          name: 'ALPEN GOLD TOWER ',
          count: 120,
          city: 'Alanya',
          district: 'Muratpaşa',
          period: '14/04/2022',
          manager: 'John Smith',
          tel: '+44 234 567 89 01',
        },
      ],
    }
  },
}
</script>

<style lang="scss">
.complex-table {
  &__row {
    display: flex;
    justify-content: space-between;
    padding: 0 18px 0 10px;
    &_header {
      border-radius: 10px;
      background-color: #f0f0f0;
    }
    &:not(:last-child) {
      margin-bottom: 15px;
    }
  }
  &__left,
  &__right {
    display: flex;
    gap: 23px;
  }

  &__col {
    padding: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 9px;
    font-weight: 500;
    white-space: nowrap;
    &_name,
    &_period {
      width: 100px;
    }
    &_name {
      display: flex;
      align-items: center;
      gap: 5px;
      text-transform: uppercase;
      font-weight: 600;
    }
    &_name,
    &_count {
      position: relative;
      svg {
        width: 10px;
        height: 10px;
      }
    }
    &_count {
      width: 44px;
      svg {
        position: absolute;
        top: 50%;
        left: 100%;
        transform: translateY(-50%);
      }
    }
    &_city,
    &_district {
      width: 50px;
    }
    &_manager {
      width: 64px;
    }
    &_tel {
      width: 84px;
    }
    &_excel,
    &_pdf {
      background-size: 19px 19px;
      background-position: center center;
      background-repeat: no-repeat;
    }
  }
  &__row_header &__col {
    font-weight: 700;
    white-space: normal;
    text-transform: none;

    &_excel {
      background-image: url(../assets/img/excel-icon.png);
    }
    &_pdf {
      background-image: url(../assets/img/pdf-icon.png);
    }
  }
}
</style>
