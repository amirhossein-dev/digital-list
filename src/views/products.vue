<template>
  <main>
    <div class="login-container" v-if="!toggleLoginSection">
      <div class="flex">
        <h2>اطلاعات اصلی</h2>
      </div>
      <!-- <form>
        <div class="input-label-container">
          <label class="login-label" for="username">نام </label>
          <input
            class="login-input"
            type="text"
            id="username"
            name="username"
            required
          />
        </div>
        <div class="input-label-container">
          <label class="login-label" for="password">نام خانوادگی </label>
          <input
            class="login-input"
            type="password"
            id="password"
            name="password"
            required
          />
        </div>
        <div class="input-label-container">
          <label class="login-label" for="password">موبایل </label>
          <input
            class="login-input"
            type="password"
            id="password"
            name="password"
            required
          />
        </div>
        <div class="input-label-container">
          <label class="login-label" for="password">مرکز </label>
          <input
            class="login-input"
            type="password"
            id="password"
            name="password"
            required
          />
        </div>
        <input type="submit" value="ورود" @click="toggleActive" />
      </form> -->
    </div>
    <div v-if="toggleLoginSection">
      <h1>محصولات</h1>
      <div class="products-container">
        <!-- PRODUCT-SECTION -->

        <div class="product">
          <div class="product-card-header">
            <div class="product-card-header-title">
              <span
                style="
                  font-weight: bolder;
                  font-size: 1.1rem;
                  padding-bottom: 0.4rem;
                "
                >مداد شمعی
              </span>
            </div>
            <div class="product-card-header-btn-container">
              <button
                class="products-btn products-btn-add"
                id="pr-btn"
                @click="toggleProduct"
              >
                <i class="fa fa-chevron-down"></i>
              </button>
            </div>
          </div>
          <Transition name="fade">
            <div
              class="product-content"
              v-if="toggleProductsSection"
              id="product"
            >
              <div class="products-input-container">
                <label class="" for="count">تعداد </label>
                <button class="products-btn btn-green" @click="incVal">
                  <i class="fa fa-plus"></i>
                </button>
                <input
                  v-model="count"
                  class="products-input"
                  style="text-align: center"
                  type="count"
                  id="count"
                  name="count"
                  required
                />
                <button class="products-btn btn-red" @click="decVal">
                  <i class="fa fa-minus"></i>
                </button>
              </div>
              <div class="products-input-container">
                <label class="" for="brand">برند </label>
                <select
                  name="cars"
                  id="brand"
                  style="
                    width: 30%;
                    font-weight: 800;
                    font-size: 1rem;
                    margin-left: 5rem;
                    border: none;
                  "
                >
                  <option value="volvo">برند 1</option>
                  <option value="saab">برند 2</option>
                  <option value="opel">برند 3</option>
                  <option value="audi">برند 4</option>
                </select>
              </div>
              <div class="products-input-container">
                <label class="" for="suggestBrand">برند پیشنهادی </label>
                <input
                  class="products-input"
                  type="suggestBrand"
                  id="suggestBrand"
                  name="suggestBrand"
                  required
                  style="margin-left: 3.6rem"
                />
              </div>
              <div class="products-input-container">
                <label for="extra-info">توضیحات </label>
                <textarea
                  rows="2"
                  cols="30"
                  maxlength="200"
                  id="extra-info"
                  class="products-input"
                ></textarea>
              </div>
            </div>
          </Transition>
        </div>

        <div class="product">
          <!-- <div class="product-card-header">
            <div><span>مداد شمعی </span></div>
            <div>
              <button class="products-btn" id="pr-btn" @click="toggleProduct()">
                <i class="fa fa-chevron-down"></i>
              </button>
            </div>
          </div> -->
          <!--          <Transition name="fade">
          <div
            class="product-content"
            id="product"
            v-if="toggleProductsSection"
          >
 <div class="products-input-container">
                             <label class="" for="count">تعداد </label>-->
          <!--                <button class="products-btn btn-green" onclick="incVal()">-->
          <!--                  <i class="fa fa-plus"></i>-->
          <!--                </button>-->
          <!--                <input value="0" class="products-input" style="text-align: center" type="count" id="count" name="count"-->
          <!--                  required />-->
          <!--                <button class="products-btn btn-red" onclick="decVal()">-->
          <!--                  <i class="fa fa-minus"></i>-->
          <!--                </button>
              <form>
                <div class="input-label-container">
                  <label class="login-label" for="username">نام </label>
                  <input
                    class="login-input"
                    type="text"
                    id="username"
                    name="username"
                    required
                  />
                </div>
                <div class="input-label-container">
                  <label class="login-label" for="password"
                    >نام خانوادگی
                  </label>
                  <input
                    class="login-input"
                    type="password"
                    id="password"
                    name="password"
                    required
                  />
                </div>
              </form>
            </div> -->

          <!--              <form>-->
          <!--                <div class="input-label-container">-->
          <!--                  <label class="login-label" for="username">نام </label>-->
          <!--                  <input class="login-input" type="text" id="username" name="username" required />-->
          <!--                </div>-->
          <!--                <div class="input-label-container">-->
          <!--                  <label class="login-label" for="password">نام خانوادگی </label>-->
          <!--                  <input class="login-input" type="password" id="password" name="password" required />-->
          <!--                </div>-->
          <!--              </form>-->

          <!--              <div class="products-input-container">-->
          <!--                <label class="" for="brand">برند </label>-->
          <!--                <select name="cars" id="brand" style="-->
          <!--                width: 30%;-->
          <!--                font-weight: 800;-->
          <!--                font-size: 1rem;-->
          <!--                margin-left: 5rem;-->
          <!--                border: none;-->
          <!--              ">-->
          <!--                  <option value="volvo">برند 1</option>-->
          <!--                  <option value="saab">برند 2</option>-->
          <!--                  <option value="opel">برند 3</option>-->
          <!--                  <option value="audi">برند 4</option>-->
          <!--                </select>-->
          <!--              </div>-->
          <!--              <div class="products-input-container">-->
          <!--                <label class="" for="suggestBrand">برند پیشنهادی </label>-->
          <!--                <input class="products-input" type="suggestBrand" id="suggestBrand" name="suggestBrand" required-->
          <!--                  style="margin-left: 3.6rem" />-->
          <!--              </div>-->
          <!--              <div class="products-input-container">-->
          <!--                <label for="extra-info">توضیحات </label>-->
          <!--                <textarea rows="2" cols="30" maxlength="200" id="extra-info" class="products-input"></textarea>-->
          <!--              </div>-->
          <!-- </div> -->
          <!--          </Transition>-->
        </div>
      </div>
    </div>
    <input v-if="toggleLoginSection" type="submit" value="ثبت خرید" />
  </main>
</template>
<script setup>
import { ref } from "vue";

const toggleLoginSection = ref(true);
const toggleProductsSection = ref(false);
const prEl = ref(null);
const count = ref(0);

const productEl = document.getElementById("product");

function toggleActive() {
  toggleLoginSection.value = !toggleLoginSection.value;
}
const toggleProduct = () => {
  toggleProductsSection.value = !toggleProductsSection.value;
  productEl.classList.toggle("hide");
};

const incVal = () => {
  count.value++;
};

const decVal = () => {
  count.value--;
};
</script>

<style scoped>
* {
  direction: rtl;
  font-family: "Lalezar", cursive;
  font-family: "Poppins", sans-serif;
  font-family: "Sedgwick Ave", cursive;
  font-family: "Vazirmatn", sans-serif;
  font-weight: 800;
}

body {
  background-color: #f1f1f1;
  font-family: Arial, sans-serif;
}

.login-container {
  width: 89%;
  margin: 20px auto;
  background-color: #ffffff;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

.products-container {
  width: 89%;
  margin: 20px auto;
  border-radius: 10px;
}

.product {
  display: flex;
  background-color: #ffffff;
  flex-direction: column;
  border-radius: 5px;
  margin-bottom: 1rem;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

.product-card-header {
  display: flex;
  flex-direction: column;
  padding: 15px 20px;
}
.product-card-header-title {
  display: flex;
  justify-content: center;
}
.product-card-header-btn-container {
  display: flex;
  justify-content: center;
}

.product-content {
  border-right: none;
  border-left: none;
  display: flex;
  flex-direction: column;
  border-top: 1px solid #cbcbcb;
  padding: 20px;
}

#product {
  height: 190px;
  transition: all 0.5s;
}

#product.hide {
  height: 0;
  opacity: 0;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.products-input-container {
  display: flex;
  justify-content: space-between;
  margin: 0.5rem 0rem;
}

.products-input {
  border: none;
}

.products-label {
  position: absolute;
  display: block;
  font-size: 15px;
  color: #333333;
  right: 1.4rem;
  bottom: 3.3rem;
  padding: 0px 2px;
  background: white;
  border-radius: 5px;
}

.products-btn {
  background-color: DodgerBlue;
  border: none;

  color: white;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}
.products-btn-add {
  width: 100%;
  background-color: rgb(8, 128, 8);
}
.products-btn-add:hover {
  width: 100%;
  background-color: rgb(9, 92, 9);
}
.btn-red {
  background-color: rgb(199, 20, 20);
}

.btn-green {
  background-color: green;
}

.products-btn i {
  transition: 0.5s;
}

.products-btn.active i {
  transform: rotate(90deg);
}

.products-btn:hover {
  background-color: RoyalBlue;
}
.products-btn-add:hover {
  width: 100%;
  background-color: rgb(9, 92, 9);
}
.btn-red:hover {
  background-color: rgb(165, 20, 20);
}

.btn-green:hover {
  background-color: rgb(2, 107, 2);
}

.flex {
  display: flex;
  justify-content: start;
  margin: 1rem 0;
}

h1 {
  text-align: center;
  color: #333333;
  margin-bottom: 20px;
}

.login-label {
  position: absolute;
  display: block;
  font-size: 15px;
  color: #333333;
  right: 1.4rem;
  bottom: 3.3rem;
  padding: 0px 6px;
  background: white;
  border-radius: 5px;
}

/* input[type="text"],
input[type="password"]  */
.login-input {
  width: 100%;
  border-radius: 5px;
  /* border: none; */
  margin-bottom: 20px;
  box-sizing: border-box;
  border: 1px solid #41301e6b;
  height: 44px;
  line-height: 44px;
}

.login-input:focus {
  /* transition: border-color 0.5s ease-in-out;     */
  border: 1px solid #41301e6b;

  transition: 0.3s;
}

input[type="submit"] {
  background-color: #eb9128;
  color: #ffffff;
  padding: 10px 20px;
  border-radius: 5px;
  border: none;
  cursor: pointer;
  font-size: 18px;
  width: 100%;
}

.input-label-container {
  display: flex;
  position: relative;
  margin: 1rem 0;
}

@media (min-width: 768px) {
  /* styles for screens wider than 768px */
  .login-container {
    width: 400px;
    margin: 50px auto;
  }

  .products-container {
    width: 400px;
    margin: 50px auto;
  }
}

.fade-enter-active,
.fade-leave-active {
  height: 190px;
  transition: all 0.3s;
}

.fade-enter-from,
.fade-leave-to {
  height: 0;
  opacity: 0;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
</style>
