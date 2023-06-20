<template>
  <main>
    <div class="login-container" v-if="toggleLoginSection">
      <div class="flex">
        <h2>اطلاعات اصلی</h2>
      </div>
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
          <label class="login-label" for="mobile">موبایل </label>
          <input
            class="login-input"
            type="mobile"
            id="mobile"
            name="mobile"
            required
          />
        </div>
        <div class="input-label-container">
          <!-- <label class="login-label" for="or">مرکز </label>
          <input
            class="login-input"
            type="or"
            id="or"
            name="or"
            required
          /> -->
        </div>
        <input type="submit" value="ورود" @click="toggleActive" />
      </form>
    </div>
    <div v-if="toggleLoginSection">
      <!-- <h1>محصولات</h1> -->
      <div class="products-container">
        <!-- PRODUCT-SECTION -->

        <!--      -->
      </div>
    </div>
    <input
      v-if="!toggleLoginSection"
      class="footer-button"
      type="submit"
      value="ثبت خرید"
    />
  </main>
</template>
<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";
// const axios = require("axios");
const toggleLoginSection = ref(true);
const toggleProductsSection = ref(false);
const count = ref(0);

const mockData = {
  success: true,
  brands: [
    {
      id: 31,
      user_id: "1",
      slug: "arya",
      title: "\u0622\u0631\u06cc\u0627",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: null,
      deleted_at: null,
      created_at: "2022-05-24T00:36:07.000000Z",
      updated_at: "2022-05-24T00:36:07.000000Z",
      href: "\/brands\/arya",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "31",
          lang: "fa",
          title: "\u0622\u0631\u06cc\u0627",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 468,
      user_id: "1",
      slug: "arzhang",
      title: "\u0627\u0631\u0698\u0646\u06af",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: "2022-06-29 22:07:14",
      deleted_at: null,
      created_at: "2022-05-24T00:36:12.000000Z",
      updated_at: "2022-06-29T22:07:14.000000Z",
      href: "\/brands\/arzhang",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "468",
          lang: "fa",
          title: "\u0627\u0631\u0698\u0646\u06af",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 735,
      user_id: "1",
      slug: "palmo",
      title: "\u067e\u0627\u0644\u0645\u0648",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: null,
      deleted_at: null,
      created_at: "2022-05-24T00:36:15.000000Z",
      updated_at: "2022-05-24T00:36:15.000000Z",
      href: "\/brands\/palmo",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "735",
          lang: "fa",
          title: "\u067e\u0627\u0644\u0645\u0648",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 765,
      user_id: "1",
      slug: "picaso",
      title: "\u067e\u06cc\u06a9\u0627\u0633\u0648",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: null,
      deleted_at: null,
      created_at: "2022-05-24T00:36:16.000000Z",
      updated_at: "2022-05-24T00:36:16.000000Z",
      href: "\/brands\/picaso",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "765",
          lang: "fa",
          title: "\u067e\u06cc\u06a9\u0627\u0633\u0648",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 880,
      user_id: "1",
      slug: "sib",
      title: "\u0633\u06cc\u0628",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: null,
      deleted_at: null,
      created_at: "2022-05-24T00:36:17.000000Z",
      updated_at: "2022-05-24T00:36:17.000000Z",
      href: "\/brands\/sib",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "880",
          lang: "fa",
          title: "\u0633\u06cc\u0628",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 3555,
      user_id: "1",
      slug: "toto",
      title: "\u062a\u0648\u062a\u0648",
      thumbnail: null,
      post_type: "brands",
      status: "1",
      published_at: null,
      deleted_at: null,
      created_at: "2022-08-03T17:07:00.000000Z",
      updated_at: "2022-08-03T17:07:00.000000Z",
      href: "\/brands\/toto",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "3555",
          lang: "fa",
          title: "\u062a\u0648\u062a\u0648",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 5416,
      user_id: "1",
      slug: "\u0622\u0631\u062a-\u0644\u0627\u06cc\u0646",
      title: "\u0622\u0631\u062a \u0644\u0627\u06cc\u0646",
      thumbnail: null,
      post_type: "brands",
      status: "0",
      published_at: null,
      deleted_at: null,
      created_at: "2023-06-20T07:07:49.000000Z",
      updated_at: "2023-06-20T07:07:49.000000Z",
      href: "\/brands\/\u0622\u0631\u062a-\u0644\u0627\u06cc\u0646",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "5416",
          lang: "fa",
          title: "\u0622\u0631\u062a \u0644\u0627\u06cc\u0646",
        },
      ],
      thumbnail_attachment: null,
    },
    {
      id: 5417,
      user_id: "1",
      slug: "\u0644\u0648\u06a9\u06cc",
      title: "\u0644\u0648\u06a9\u06cc",
      thumbnail: null,
      post_type: "brands",
      status: "0",
      published_at: null,
      deleted_at: null,
      created_at: "2023-06-20T07:08:12.000000Z",
      updated_at: "2023-06-20T07:08:12.000000Z",
      href: "\/brands\/\u0644\u0648\u06a9\u06cc",
      thumbnailUrl: null,
      translates: [
        {
          post_id: "5417",
          lang: "fa",
          title: "\u0644\u0648\u06a9\u06cc",
        },
      ],
      thumbnail_attachment: null,
    },
  ],
  categories: [
    {
      id: 265,
      post_type: "organizationOrders",
      slug: "\u0645\u062f\u0627\u062f-\u0631\u0646\u06af\u06cc",
      title: "\u0645\u062f\u0627\u062f \u0631\u0646\u06af\u06cc",
      serp_title: null,
      excerpt: null,
      content: null,
      image: null,
      data: null,
      lang: "fa",
      parent: null,
      created_at: "2023-06-20T06:59:00.000000Z",
      updated_at: "2023-06-20T07:00:01.000000Z",
      href: "categories\/organizationOrders\/\u0645\u062f\u0627\u062f-\u0631\u0646\u06af\u06cc",
      translates: [
        {
          category_id: "265",
          lang: "fa",
          title: "\u0645\u062f\u0627\u062f \u0631\u0646\u06af\u06cc",
        },
      ],
      attributes: [
        {
          id: 45,
          title: "\u062a\u0639\u062f\u0627\u062f \u0631\u0646\u06af",
          description: ".",
          icon: null,
          type: "category",
          lang: "fa",
          parent: null,
          created_at: "2023-06-20T06:59:53.000000Z",
          updated_at: "2023-06-20T07:01:24.000000Z",
          pivot: {
            category_id: "265",
            attribute_id: "45",
          },
          keys: [
            {
              id: 149,
              title: "6 \u0631\u0646\u06af",
              description: "",
              icon: null,
              lang: "fa",
              parent: null,
              created_at: "2023-06-20T06:59:21.000000Z",
              updated_at: "2023-06-20T06:59:21.000000Z",
              pivot: {
                attribute_id: "45",
                attribute_key_id: "149",
              },
              translates: [
                {
                  attribute_key_id: "149",
                  lang: "fa",
                  title: "6 \u0631\u0646\u06af",
                  description: null,
                },
              ],
            },
            {
              id: 150,
              title: "12 \u0631\u0646\u06af",
              description: "",
              icon: null,
              lang: "fa",
              parent: null,
              created_at: "2023-06-20T06:59:26.000000Z",
              updated_at: "2023-06-20T06:59:26.000000Z",
              pivot: {
                attribute_id: "45",
                attribute_key_id: "150",
              },
              translates: [
                {
                  attribute_key_id: "150",
                  lang: "fa",
                  title: "12 \u0631\u0646\u06af",
                  description: null,
                },
              ],
            },
            {
              id: 151,
              title: "24 \u0631\u0646\u06af",
              description: "",
              icon: null,
              lang: "fa",
              parent: null,
              created_at: "2023-06-20T06:59:30.000000Z",
              updated_at: "2023-06-20T06:59:30.000000Z",
              pivot: {
                attribute_id: "45",
                attribute_key_id: "151",
              },
              translates: [
                {
                  attribute_key_id: "151",
                  lang: "fa",
                  title: "24 \u0631\u0646\u06af",
                  description: null,
                },
              ],
            },
            {
              id: 152,
              title: "36 \u0631\u0646\u06af",
              description: "",
              icon: null,
              lang: "fa",
              parent: null,
              created_at: "2023-06-20T06:59:38.000000Z",
              updated_at: "2023-06-20T06:59:38.000000Z",
              pivot: {
                attribute_id: "45",
                attribute_key_id: "152",
              },
              translates: [
                {
                  attribute_key_id: "152",
                  lang: "fa",
                  title: "36 \u0631\u0646\u06af",
                  description: null,
                },
              ],
            },
          ],
          translates: [
            {
              attribute_id: "45",
              lang: "fa",
              title: "\u062a\u0639\u062f\u0627\u062f \u0631\u0646\u06af",
              description: ".",
            },
          ],
        },
      ],
    },
  ],
  organizations: [
    {
      id: 1,
      title: "\u0645\u0647\u062f\u06a9\u0648\u062f\u06a9",
    },
    {
      id: 2,
      title: "\u0645\u062f\u0631\u0633\u0647",
    },
    {
      id: 3,
      title: "\u0633\u0627\u0632\u0645\u0627\u0646",
    },
    {
      id: 4,
      title: "\u0633\u0627\u06cc\u0631",
    },
  ],
};

const mockArray = ["", "", "", "", "", ""];
const selectedOption = ref(null);
const attrSelectedOption = ref(null);
function toggleActive() {
  toggleLoginSection.value = !toggleLoginSection.value;
}
function getAllData() {
  const response = axios.get(
    "https://api.aryaland.ir/v1/aryaland/digital-list"
  );
  console.log(response);
}

onMounted(() => {
  getAllData();
  console.log("somthing");
});

const toggleProduct = () => {
  toggleProductsSection.value = !toggleProductsSection.value;
  console.log(mockData);
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
  background-color: white;
  border: 2px solid rgb(0, 168, 0);
  border-radius: 0.4rem;
  cursor: pointer;
}
.products-btn-add:hover {
  width: 100%;
  background-color: rgb(206, 206, 206);
}
.btn-red {
  height: 2.5rem;
  background-color: white;
  border: 2px solid rgb(168, 0, 0);
  border-radius: 0.4rem;
  cursor: pointer;
}

.btn-green {
  height: 2.5rem;
  background-color: white;
  border: 2px solid rgb(0, 168, 0);
  border-radius: 0.4rem;
  cursor: pointer;
}

/* .products-btn:hover {
  background-color: RoyalBlue;
} */

.btn-red:hover {
  background-color: rgb(206, 206, 206);
}

.btn-green:hover {
  background-color: rgb(206, 206, 206);
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

.product-label {
  position: absolute;
  display: block;
  font-size: 15px;
  color: #333333;
  right: 1.4rem;
  bottom: 3.3rem;
  padding: 0px 6px;
  background: white;
  border-radius: 5px;
  right: 4.6rem;
  bottom: 2.2rem;
}
.product-select-box-label {
  position: absolute;
  display: block;
  font-size: 15px;
  color: #333333;
  bottom: 3.3rem;
  padding: 0px 6px;
  background: white;
  border-radius: 5px;
  right: 1rem;
  bottom: 2.2rem;
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
.products-input {
  width: 70%;
  border-radius: 5px;
  /* border: none; */
  margin-bottom: 20px;
  box-sizing: border-box;
  border: 1px solid #41301e6b;
  height: 44px;
  line-height: 44px;
  text-align: center;
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
.products-input-label-container {
  display: flex;
  height: 3rem;
  position: relative;
  margin: 1.3rem 0;
}

.select-box {
  width: 100%;
  line-height: 44px;
  height: 50px;
  text-align: center;
  border-radius: 0.4rem;
  border-color: #41301e6b;
  margin: 0.3rem 0;
}

.footer-button {
  position: fixed;
  bottom: 0;
  right: 0;
  left: 0;
  margin-bottom: 2rem;
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
