<template>
  <form class="complex-form">
    <div class="complex-form__field complex-form__field_col">
      <label for="choose-complex" class="complex-form__label">Выбрать ЖК</label>
      <div class="complex-form__input complex-form__input_dropdown">
        <select name="complex" id="choose-complex" v-model="activeComplex">
          <option
            v-for="(complex, idx) in complexes"
            :key="idx"
            :value="complex.id"
          >
            {{ complex.name }}
          </option>
        </select>
      </div>
    </div>
    <div class="complex-form__field complex-form__field_col">
      <label for="choose-manager" class="complex-form__label"
        >Назначить управляющего</label
      >
      <div class="complex-form__input">
        <input type="text" id="choose-manager" />
      </div>
    </div>
    <div class="complex-form__data" v-if="activeComplexData">
      <div class="complex-form__label">Данные ЖК</div>
      <div class="complex-form__complex-data complex-data">
        <div class="complex-data__row">
          <span class="complex-data__title">Телефон:</span>
          <span class="complex-data__value">{{ activeComplexData.tel }}</span>
        </div>
        <div class="complex-data__row">
          <span class="complex-data__title">E-mail:</span>
          <span class="complex-data__value">{{ activeComplexData.email }}</span>
        </div>
        <div class="complex-data__row">
          <span class="complex-data__title">Адрес:</span>
          <span class="complex-data__value">{{
            activeComplexData.address
          }}</span>
        </div>

        <div class="complex-data__row">
          <span class="complex-data__title">IBAN</span>
          <span class="complex-data__value">{{ activeComplexData.iban }}</span>
        </div>
        <div class="complex-data__row">
          <span class="complex-data__title">Банк:</span>
          <span class="complex-data__value">{{ activeComplexData.bank }}</span>
        </div>
        <div class="complex-data__row">
          <span class="complex-data__title">Получатель:</span>
          <span class="complex-data__value">{{
            activeComplexData.reciever
          }}</span>
        </div>
      </div>
    </div>
    <div class="complex-form__field">
      <label for="start-date" class="complex-form__label">Дата начала</label>
      <div
        class="complex-form__input complex-form__input_small complex-form__input_dropdown"
      >
        <input type="date" id="start-date" />
      </div>
    </div>
    <div class="complex-form__field">
      <label for="end-date" class="complex-form__label">Дата завершения</label>
      <div
        class="complex-form__input complex-form__input_small complex-form__input_dropdown"
      >
        <input type="date" id="end-date" />
      </div>
    </div>
    <div class="complex-form__field">
      <label for="balance" class="complex-form__label">Начальный остаток</label>
      <div class="complex-form__input complex-form__input_small">
        <input type="text" id="balance" />
      </div>
    </div>

    <div class="complex-form__btns">
      <button class="complex-form__add-btn">Создать хранилище</button>
      <button class="complex-form__save-btn">
        Сохранить и перейти в профиль ЖК
      </button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      complexes: [
        {
          id: 1,
          name: 'SEA PEARL GARDEN',
          tel: '+7  916 555 44 33',
          email: 'mail@mail.ru',
          address: 'Alanya, Mahmutlar, Gazipaşa Cd, no:54',
          iban: 'TR01 2345 3456 5678 7890 22',
          bank: 'GARANTI BANK',
          reciever: 'Sea Pearl Garden Yonetimi',
        },
        {
          id: 2,
          name: 'GOLDCITY AURA 3',
          tel: '+90 535 111 22 33',
          email: 'mail11@mail.ru',
          address: 'Alanya, Mahmutlar, Gazipaşa Cd, no:55',
          iban: 'TR01 2345 3456 5678 7890 33',
          bank: 'GARANTI BANK ',
          reciever: 'Sea Pearl Garden Yonetimi',
        },
        {
          id: 3,
          name: 'ALPEN GOLD TOWER ',
          tel: '+44 234 567 89 01',
          email: 'mail22@mail.ru',
          address: 'Alanya, Mahmutlar, Gazipaşa Cd, no:88',
          iban: 'TR01 2345 3456 5678 7890 44',
          bank: 'GARANTI BANK ',
          reciever: 'Sea Pearl Garden Yonetimi',
        },
      ],
      activeComplex: null,
    }
  },

  computed: {
    activeComplexData() {
      return this.complexes.find((complex) => complex.id === this.activeComplex)
    },
  },
}
</script>

<style lang="scss">
.complex-form {
  display: flex;
  flex-direction: column;
  &__field {
    width: 250px;
    display: flex;
    justify-content: space-between;
    gap: 15px;
    align-items: center;
    &:not(:last-child) {
      margin-bottom: 20px;
    }
    &_col {
      width: 200px;
      gap: 0;
      flex-direction: column;
      align-items: start;
      &:not(:last-child) {
        margin-bottom: 30px;
      }
    }
  }
  &__label {
    font-size: 12px;
    font-weight: 500;
  }
  &__field_col &__label {
    margin-bottom: 10px;
  }
  &__input {
    width: 100%;

    input,
    select {
      width: 100%;
      height: 100%;
      padding: 5px;
      border-radius: 5px;
      border: 1px solid #621280;
      background-color: #fff;
      font-size: 10px;
      font-weight: 500;
    }

    input::-webkit-calendar-picker-indicator {
      opacity: 0;
    }

    input[type='date']::-webkit-input-placeholder {
      opacity: 0;
    }

    &_small {
      width: 95px;
    }
    &_dropdown {
      position: relative;
      &:after {
        content: '';
        position: absolute;
        top: 50%;
        right: 3px;
        transform: translateY(-50%);
        width: 0px;
        height: 0px;
        border-style: solid;
        border-width: 9px 7px 0 7px;
        border-radius: 5px;
        border-color: #621280 transparent transparent transparent;
        pointer-events: none;
      }
    }
  }
  &__data {
    width: 347px;
    margin-bottom: 24px;
  }
  &__data &__label {
    margin-bottom: 10px;
  }
  &__complex-data {
    width: 100%;
    padding: 8px 14px;
    border-radius: 5px;
    border: 1px solid #621280;
    background-color: #fff;
  }
  &__btns {
    width: 100%;
    margin-top: auto;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }
  &__add-btn {
    width: 200px;
    padding: 5px;
    border-radius: 5px;
    border: 1px solid #621280;
    background-color: #fff;
    font-size: 10px;
    font-weight: 500;
    transition: color 0.3s ease, background-color 0.4s ease;
    &:hover {
      color: #fff;
      background-color: #621280;
    }
  }
  &__save-btn {
    width: 265px;
    background-color: #4dcc1d;
    color: #fff;
    font-size: 10px;
    font-weight: 600;
    padding: 10px;
    border-radius: 5px;
    transition: background-color 0.4s ease;
    &:hover {
      background-color: #7cff4c;
    }
  }
}
.complex-data {
  &__row {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    font-size: 10px;
    font-weight: 500;
    &:not(:last-child) {
      margin-bottom: 12px;
    }
  }
  &__title {
    opacity: 0.5;
  }
  &__value {
    font-weight: 600;
  }
}
</style>
