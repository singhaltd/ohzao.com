
<script setup>
const cateGory = await $fetch("https://dummyjson.com/products/categories");
const ProductList = await $fetch(
  "https://dummyjson.com/products?limit=100&skip=1"
);
</script>

<style>
</style>
<template>
  <div class="max-w-7xl mx-auto">
    <section class="contianer">
      <div class="flex">
        <!-- <CarouselAdslider /> -->
        <div class="rounded">
          <img
            src="https://icms-image.slatic.net/images/ims-web/f47b9e3a-27ca-4c43-b516-d6be3625f3bc.jpg"
            class="w-[100%]"
          />
        </div>
      </div>
    </section>
    <section class="pb-5 pt-[30px]">
      <h1>ໝວດໝູ່</h1>
      <CarouselCategory />
      <div class="flex gap-2 w-full overflow-x-auto">
        <div
          class="justify-center px-3 py-3 bg-neutral-200 rounded-xl"
          v-for="(ix, i) in cateGory"
          :key="i"
        >
          <img
            :src="'/category/' + ix + '.png'"
            class="w-12"
            alt=""
            srcset=""
          />
          <p class="text-[14px]">{{ ix }}</p>
        </div>
      </div>
    </section>
    <section>
      <div class="flex justify-scpace-between">
        <h1 class="text-xl leading-7 font-medium py-3">ສິນຄ້າທັງໝົດ</h1>
        <a href="#" class="text-md leading-7 font-medium py-3">view More</a>
      </div>
      <!-- {{ ProductList }} -->
      <div class="grid grid-cols-7 gap-2">
        <ProductCard
          v-for="(pt, i) in ProductList.products"
          :attr="pt"
          :key="i"
        />
      </div>
      <button>Load More</button>
    </section>
    <!-- <section>
      <div class="px-2">
        <h1>Latest Discounted Products</h1>
      </div>
      <div class="grid lg:grid-cols-7 md:grid-cols-2 gap-2">
        <ProductCard v-for="i in 20" :key="i" />
      </div>
    </section> -->
  </div>
</template>
