<script setup>
import { ref } from "vue";

const clickChecker = ref(false);
function showOrClose() {
  clickChecker.value = !clickChecker.value;
  const orderArrayBtn = document.querySelector(".order__item-array");
  const orderItemComponents = document.querySelector(".order__item-components");

  const list = document.querySelector(".components__operations-list");
  const decoration = document.querySelector(
    ".components__operations-list__decoration"
  );
  const btn = document.querySelector(".components__operations-list__btn");

  if (clickChecker.value == true) {
    orderArrayBtn?.classList?.add("active");
    orderItemComponents?.classList?.add("active");
  } else if (clickChecker.value == false) {
    orderArrayBtn?.classList?.remove("active");
    orderItemComponents?.classList?.remove("active");
    list.classList.remove("active");
    decoration.classList.remove("active");
    btn.classList.remove("active");
  }
}

const clickListChecker = ref(false);

function showOrCloseList() {
  clickListChecker.value = !clickListChecker.value;

  const list = document.querySelector(".components__operations-list");
  const decoration = document.querySelector(
    ".components__operations-list__decoration"
  );
  const btn = document.querySelector(".components__operations-list__btn");

  if (clickListChecker.value == true) {
    list.classList.add("active");
    decoration.classList.add("active");
    btn.classList.add("active");
  } else {
    list.classList.remove("active");
    decoration.classList.remove("active");
    btn.classList.remove("active");
  }
}
</script>

<template>
  <main>
    <section class="order">
      <div class="container">
        <ul class="order__list">
          <li class="order__item">
            <div class="order__item-status">
              <img
                src="./assets/images/Delivery.svg"
                alt=""
                class="order__item-status__img"
              />

              <img
                src="./assets/images/ArrowDownUp.svg"
                alt=""
                class="order__item-array"
                @click="showOrClose"
              />
            </div>

            <div class="order__item-data">
              <div class="order__item-data__tab">
                <span class="order__item-id order__item-info"
                  >ID:<span>21112</span></span
                >
                <div class="order__item-details order__item-info">
                  <span class="order__item-order__num">№73123</span>
                  <span class="order__item-order__date"
                    >03.03.2024 9:21:24</span
                  >
                </div>

                <span class="order__item-partnerPoint order__item-info"
                  >Филиал:
                  <span>Шумерля</span>
                </span>
                <span class="order__item-client order__item-info"
                  >Клиент:
                  <span>+79603098486</span>
                </span>
                <span class="order__item-address order__item-info"
                  >Адрес доставки: <span>Moscow 12-12-12</span></span
                >
                <span class="order__item-amount order__item-info"
                  >Сумма заказа: <span>999 ₽</span></span
                >
                <span class="order__item-paymentType order__item-info"
                  >Способ оплаты:
                  <span>Терминал</span>
                </span>
                <span class="order__item-orderType order__item-info"
                  >Отметки: <span>Самовывоз</span></span
                >
              </div>
            </div>

            <div class="order__item-components">
              <div class="components__wrapper">
                <div class="components__main components__box">
                  <h3
                    class="components__main-title components__box-title"
                  >
                    Заказы
                  </h3>

                  <ul class="components__main-list">
                    <li class="components__main-item">
                      <span class="components__main-item__qty">1</span>
                      <span class="components__main-item__name">
                        Сет Смарт Lorem ipsum dolor sit amet, consectetur
                        adipisicing elit. Ad dolores eum repellat incidunt
                        suscipit aspernatur odit aliquam quibusdam sit dolorem
                        reiciendis, eligendi porro pariatur dolorum culpa velit
                        quos iste facilis!
                      </span>
                      <span class="components__main-item__price">949$</span>
                    </li>
                    <li class="components__main-item">
                      <span class="components__main-item__qty">1</span>
                      <span class="components__main-item__name">
                        Сет Смарт
                      </span>
                      <span class="components__main-item__price">949$</span>
                    </li>
                    <li class="components__main-item">
                      <span class="components__main-item__qty">1</span>
                      <span class="components__main-item__name">
                        Сет Смарт
                      </span>
                      <span class="components__main-item__price">949$</span>
                    </li>
                    <li class="components__main-item">
                      <span class="components__main-item__qty">1</span>
                      <span class="components__main-item__name">
                        Сет Смарт
                      </span>
                      <span class="components__main-item__price">949$</span>
                    </li>
                  </ul>

                  <h3
                    class="components__operations-title components__box-title"
                  >
                    Сумма
                  </h3>

                  <div class="components__main-price">
                    <div class="components__main-price__order price__order">
                      <span
                        class="components__main-price__title price__order-title"
                        >Сумма заказа</span
                      >
                      <span
                        class="components__main-price__main price__order-main"
                        >1 588,00 $</span
                      >
                    </div>
                    <div class="components__main-price__discount price__order">
                      <span
                        class="components__main-price__title price__order-title"
                        >Бонусная скидка</span
                      >
                      <span
                        class="components__main-price__main price__order-main"
                        >477,00 $</span
                      >
                    </div>
                    <div class="components__main-price__total price__order">
                      <span
                        class="components__main-price__title price__order-title"
                        >Итого</span
                      >

                      <span class="components__main-price__main"
                        >1 111,00 $</span
                      >
                    </div>
                    <div
                      class="components__main-price__paymentType price__order"
                    >
                      <span
                        class="components__main-price__title price__order-title"
                        >Способ оплаты</span
                      >
                      <span
                        class="components__main-price__main price__order-main"
                        >Терминал</span
                      >
                    </div>
                  </div>
                </div>
                <div class="components__operations components__box">
                  <h3
                    class="components__operations-title components__box-title"
                  >
                    Операции
                  </h3>

                  <ul class="components__operations-list">
                    <span
                      class="components__operations-list__decoration"
                    ></span>
                    <span
                      class="components__operations-list__btn"
                      @click="showOrCloseList"
                    >
                      <img
                        src="./assets/images/ArrowDownUp.svg"
                        alt=""
                        class=""
                      />
                    </span>

                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                    <li class="components__operations-item">
                      <div
                        class="components__operations-component components__operations-el"
                      >
                        <span
                          class="components__operations-component__title components__operations-el__title"
                          >Наименование:</span
                        >
                        <span
                          class="components__operations-component__src components__operations-el__src"
                          >Курица копченная филе</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >№: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-product components__operations-el"
                      >
                        <span
                          class="components__operations-product__title components__operations-el__title"
                          >Наименование продукта:</span
                        >
                        <span
                          class="components__operations-product__src components__operations-el__src"
                          >Цезарь 33см</span
                        >
                        <span
                          class="components__operations-component__id components__operations-el__id"
                          >ID: 1</span
                        >
                      </div>
                      <div
                        class="components__operations-qty components__operations-el"
                      >
                        <span
                          class="components__operations-qty__title components__operations-el__title"
                          >Кол-во:</span
                        >
                        <span
                          class="components__operations-qty__src components__operations-el__src"
                          >70 гр</span
                        >
                      </div>
                      <div
                        class="components__operations-priceInKg components__operations-el"
                      >
                        <span
                          class="components__operations-priceInKg__title components__operations-el__title"
                          >Цена за кг:</span
                        >
                        <span
                          class="components__operations-priceInKg__src components__operations-el__src"
                          >5$</span
                        >
                      </div>
                      <div
                        class="components__operations-totalPrice components__operations-el"
                      >
                        <span
                          class="components__operations-totalPrice__title components__operations-el__title"
                          >Стоимость:</span
                        >
                        <span
                          class="components__operations-totalPrice__src components__operations-el__src"
                          >17$</span
                        >
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<style scoped></style>
