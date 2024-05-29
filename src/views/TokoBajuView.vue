<template>
  <div class="w-full py-2 bg-violet-600 text-center text-white text-xs">
    Dapatkan Diskon 50% Sekarang!
  </div>
  <nav class="bg-white w-full sticky top-0 z-50 shadow">
    <div
      class="max-w-screen-xl mx-auto px-4 flex items-center justify-between h-20"
    >
      <a class="flex-shrink-0 ml-10" href="#">
        <img src="../assets/logo-3.png" class="h-14 w-22" alt="Logo" />
      </a>
      <div class="hidden md:flex flex-grow justify-center space-x-10 ml-10">
        <ul class="flex space-x-10">
          <li v-for="(baju, index) in bajus" :key="index">
            <a href="#" class="text-gray-900 hover:text-gray-700">{{
              baju.category
            }}</a>
          </li>
        </ul>
      </div>
      <div class="flex items-center space-x-10 pr-10">
        <button type="button" class="btn btn-outline">
          <i class="bi bi-search text-2xl"></i>
        </button>
        <button type="button" class="btn btn-outline">
          <i class="bi bi-cart3 text-2xl"></i>
        </button>
      </div>
    </div>
  </nav>
  <section id="section-1" class="relative ">
    <img
      src="../assets/island1.png"
      alt="Background"
      class="w-full lg:h-auto h-[265px] object-fill  max-h-[560px]"
    />
    <div
      class="absolute z-10 w-full h-full top-2 lg:px-20 flex flex-col items-end justify-center"
    >
      <div
        class="capitalize text-white text-xl lg:text-4xl tracking-wide leading-snug text-right"
      >
        <span>Baju</span> <b>Bagus Dan</b><br />
        <span>Keren Untuk Orang</span> <b>Casual</b><br />
      </div>
      <div
        class="cursor-pointer bg-violet-900 lg:p-4 p-2 w-40 lg:w-52 text-center text-white rounded lg:text-base text-xs mt-4 lg:mt-8 hover:opacity-70"
      >
        Dapatkan Sekarang
      </div>
    </div>
  </section>

  <section id="section-2" class="lg:py-20 py-10 w-full bg-violet-100">
    <div class="w-full text-center text-xl text-dark">
      Keuntungan Yang Kami Berikan
    </div>
    <div
      class="mt-6 lg:mt-12 w-full grid grid-cols-2 lg:flex gap-6 lg:gap-10 justify-between lg:px-20 px-4"
    >
      <div
        class="bg-white py-6 lg:w-[287px] rounded flex flex-col gap-2 col-span-1 px-4"
      >
        <div class="w-full text-center text-violet-700">
          <i class="bi bi-truck-flatbed text-5xl"></i>
        </div>
        <div class="text-violet-700 w-full text-center lg:text-lg">
          Bisa Pembayaran COD
        </div>
      </div>
      <div
        class="bg-white py-6 lg:w-[287px] rounded flex flex-col gap-2 col-span-1 px-4"
      >
        <div class="w-full text-center text-violet-700">
          <i class="bi bi-award text-5xl"></i>
        </div>
        <div class="text-violet-700 w-full text-center lg:text-lg">
          Barang Original
        </div>
      </div>
      <div
        class="bg-white py-6 lg:w-[287px] rounded flex flex-col gap-2 col-span-1 px-4"
      >
        <div class="w-full text-center text-violet-700">
          <i class="bi bi-shield-check text-5xl"></i>
        </div>
        <div class="text-violet-700 w-full text-center lg:text-lg">
          Kualitas Terjamin
        </div>
      </div>
      <div
        class="bg-white py-6 lg:w-[287px] rounded flex flex-col gap-2 col-span-1 px-4"
      >
        <div class="w-full text-center text-violet-700">
          <i class="bi bi-tags text-5xl"></i>
        </div>
        <div class="text-violet-700 w-full text-center lg:text-lg">
          Pembayaran Terpercaya
        </div>
      </div>
    </div>
  </section>
  <section id="section-3" class="py-16 lg:px-20 px-4 flex flex-col gap-10">
    <div class="w-full text-start text-xl text-dark">Kategori Produk</div>
    <div class="w-[362px] md:w-full overflow-x-auto">
      <div class="flex w-full flex-wrap">
        <div
          v-for="(baju, index) in bajus"
          :key="index"
          :class="getClass(index)"
        >
          {{ baju.category }}
        </div>
      </div>
    </div>
  </section>
  <section
    id="section-5"
    class="py-8 lg:py-16 lg:px-20 px-4 flex flex-col gap-10"
  >
    <div v-for="(baju, index) in bajus" :key="index" class="w-full">
      <div class="w-full text-start text-xl text-dark mb-10">
        {{ baju.category }}
      </div>
      <div class="grid grid-cols-2 lg:grid-cols-5 gap-4">
        <div
          v-for="(product, productIndex) in baju.products"
          :key="productIndex"
          class="bg-violet-100 rounded"
        >
          <div>
            <img
              :alt="product.name"
              class="w-full h-56 object-cover image-lazy pulse"
              :src="product.image"
            />
          </div>
          <div class="flex flex-col gap-1 mx-3 lg:mx-4 mb-4 mt-3">
            <div class="text-dark text-sm font-medium">{{ product.name }}</div>
            <div class="flex items-center gap-1">
              <i
                v-for="n in product.rating"
                :key="n"
                class="bi bi-star-fill text-xs text-yellow-600"
              ></i>
            </div>
            <div class="flex justify-between w-full items-center">
              <div class="text-dark font-medium text-sm">
                {{ product.price }}$
              </div>
              <div
                class="bg-violet-300 w-8 h-8 flex items-center justify-center rounded-full cursor-pointer hover:opacity-60"
              >
                <i class="bi bi-cart-plus text-lg text-white"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="w-full text-center hover:opacity-60 text-dark mt-8">
        <a href="#" class="">Lihat Semuanya</a>
      </div>
    </div>
  </section>
  <section
    id="section-9"
    class="py-8 lg:py-16 lg:px-20 px-4 flex flex-col gap-10 bg-violet-100"
  >
    <div class="w-full text-center text-xl text-dark">Testimoni Pelanggan</div>
    <div class="flex space-x-3">
      <div class="flex-1 bg-violet-400 text-center p-8">
        <i class="bi bi-person-fill text-white text-4xl"></i>
        <div class="font-semibold text-white text-2xl">Alan adi wijaya</div>
        <div class="text-white">Lorem ipmsum dolar sit amet</div>
      </div>
      <div class="flex-1 bg-violet-400 text-center p-8">
        <i class="bi bi-person-fill text-white text-4xl"></i>
        <div class="font-semibold text-white text-2xl">Alan adi wijaya</div>
        <div class="text-white">Lorem ipmsum dolar sit amet</div>
      </div>
    </div>
  </section>
  <section
    id="section-9"
    class="py-8 lg:py-16 lg:px-20 px-4 flex flex-col gap-10 bg-gray-100"
  >
    <div class="w-full text-xl text-dark">Metode Pembayaran</div>
    <div class="flex gap-8">
      <div class="bg-white rounded p-4">
        <div>
          <img src="../assets/stoneIsland/dana.png" class="w-24 h-auto" />
        </div>
      </div>
      <div class="bg-white rounded p-4">
        <div>
          <img src="../assets/stoneIsland/bca.png" class="w-24 h-auto" />
        </div>
      </div>
    </div>
  </section>
  <section
    id="section-9"
    class="py-8 lg:py-16 px-4 lg:px-20 flex flex-col gap-10 bg-gray-100"
  >
    <div class="w-full text-start text-xl text-dark">Pertanyaan Umum (FAQ)</div>
    <div class="flex flex-col gap-4">
      <details
        v-for="(item, index) in faqItems"
        :key="index"
        class="bg-violet-100 cursor-pointer p-4 flex flex-col gap-2"
      >
        <summary class="flex w-full justify-between items-center text-dark">
          <div class="font-medium">{{ item.question }}</div>
          <div><i class="bi bi-chevron-down"></i></div>
        </summary>
        <div class="mt-2">{{ item.answer }}</div>
      </details>
    </div>
  </section>
  <footer>
    <div
      id="cta"
      class="bg-violet-300 py-12 w-full flex lg:flex-row flex-col gap-4 justify-between items-center px-4 lg:px-20"
    >
      <div
        class="text-xl lg:text-2xl text-center lg:text-start font-medium text-white leading-normal tracking-tighter"
      >
        Mau Baju keren & kece <br />
        beli di StoneIsland aja !
      </div>
      <div
        class="cursor-pointer bg-violet-500 p-2 lg:p-4 w-40 lg:w-52 text-sm text-center text-white rounded hover:opacity-70"
      >
        <i class="bi bi-whatsapp"></i>WhatsApp
      </div>
    </div>
    <div
      class="bg-violet-800 w-full pt-16 pb-4 px-4 lg:px-20 flex flex-col items-center lg:items-start gap-12"
    >
      <div>
        <img src="../assets/logo-3.png" alt="logo" class="w-52 h-auto" />
      </div>
      <div
        class="flex lg:flex-row flex-col lg:gap-0 gap-8 justify-center items-center lg:justify-between w-full lg:items-start"
      >
        <div class="flex flex-col gap-4 text-white text-center lg:text-start">
          <div class="font-medium lg:text-lg">Alamat</div>
          <div class="text-sm lg:text-base">Cianjur, Jawa Barat</div>
        </div>
        <div class="flex flex-col gap-4 text-white text-center lg:text-start">
          <div class="font-medium lg:text-lg">Kategori Produk</div>
          <div
            v-for="(baju, index) in bajus"
            :key="index"
            class="text-sm lg:text-base"
          >
            {{ baju.category }}
          </div>
        </div>
        <div class="flex flex-col gap-4 text-white text-center lg:text-start">
          <div class="font-medium lg:text-lg">Kontak Kami</div>
          <div class="text-sm lg:text-base">0866-6666-6666</div>
          <div class="text-sm lg:text-base">StoneIsland@shop.com</div>
        </div>
      </div>
      <div class="w-full text-center text-white text-xs">
        © 2024 Stone Island All rights reserved
      </div>
    </div>
  </footer>
</template>
<script setup>
import { reactive } from "vue";
import gm1 from "../assets/stoneIsland/gm1.png";
import gm2 from "../assets/stoneIsland/gm2.png";
import gm3 from "../assets/stoneIsland/gm3.png";
import gm4 from "../assets/stoneIsland/gm4.png";
import gm from "../assets/stoneIsland/gm.png";
import gm6 from "../assets/stoneIsland/gm6.png";
import gm7 from "../assets/stoneIsland/gm7.png";
import gm8 from "../assets/stoneIsland/gm8.png";
import gm9 from "../assets/stoneIsland/gm9.png";
import gm10 from "../assets/stoneIsland/gm10.png";
import gm11 from "../assets/stoneIsland/gm11.png";
import gm12 from "../assets/stoneIsland/gm12.png";
import gm13 from "../assets/stoneIsland/gm13.png";
import gm14 from "../assets/stoneIsland/gm14.png";
import gm15 from "../assets/stoneIsland/gm15.png";

const bajus = reactive([
  {
    category: "Jaket",
    products: [
      { name: "Jaket", price: 100, image: gm1, rating: 5 },
      { name: "Jaket", price: 100, image: gm2, rating: 5 },
      { name: "Jaket", price: 100, image: gm3, rating: 5 },
      { name: "Jaket", price: 100, image: gm4, rating: 5 },
      { name: "Jaket", price: 100, image: gm, rating: 5 },
    ],
  },
  {
    category: "T-shirt",
    products: [
      { name: "T-shirt", price: 50, image: gm6, rating: 5 },
      { name: "T-shirt", price: 50, image: gm7, rating: 5 },
      { name: "T-shirt", price: 50, image: gm8, rating: 5 },
      { name: "T-shirt", price: 50, image: gm9, rating: 5 },
      { name: "T-shirt", price: 50, image: gm10, rating: 5 },
    ],
  },
  {
    category: "Crewneck",
    products: [
      { name: "Crewneck", price: 89, image: gm11, rating: 5 },
      { name: "Crewneck", price: 89, image: gm12, rating: 5 },
      { name: "Crewneck", price: 89, image: gm13, rating: 5 },
      { name: "Crewneck", price: 89, image: gm14, rating: 5 },
      { name: "Crewneck", price: 89, image: gm15, rating: 5 },
    ],
  },
]);
const getClass = (index) => {
  return `flex-grow cursor-pointer hover:opacity-50 lg:h-36 flex justify-center items-center text-white ${
    index % 2 === 0 ? "bg-violet-400" : "bg-violet-300"
  }`;
};
import { ref } from "vue";
const faqItems = ref([
  {
    question: "lorem ipsum dolor sit amet?",
    answer: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
  },
  {
    question: "lorem ipsum dolor sit amet?",
    answer:
      "Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    question: "lorem ipsum dolor sit amet?",
    answer:
      "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
  },
  {
    question: "lorem ipsum dolor sit amet?",
    answer:
      "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
  },
]);
</script>
 