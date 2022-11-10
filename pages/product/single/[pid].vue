<script setup>
import { ref } from "vue";
const route = useRoute();
const ProductList = await $fetch(
  `https://dummyjson.com/products/${route.params.pid}`
);
let descMore = ref(false);
const HoverImage = ref(0);
</script>

<template>
  <div>
    <!-- component -->
    <!-- {{ ProductList }} -->
    <section class="text-gray-700 body-font overflow-hidden bg-white">
      <div class="container py-24 mx-auto">
        <div class="lg:w-4/5 mx-auto flex flex-wrap">
          <div class="
              lg:w-1/2
              w-full
              object-cover object-center
              rounded
              border border-gray-200
            ">
            <img alt="ecommerce" class="h-[400px]" :src="ProductList.images[HoverImage]" />
            <div class="flex">
              <img alt="ecommerce" class="w-10" v-on:mouseover="HoverImage = i" v-for="(im, i) in ProductList.images"
                :key="i" :src="im" />
            </div>
          </div>

          <div class="lg:w-1/2 w-full lg:pl-10 lg:py-6 mt-6 lg:mt-0">
            <h2 class="text-sm title-font text-gray-500 tracking-widest">
              {{ ProductList.brand }}
            </h2>
            <h1 class="text-gray-900 text-3xl title-font font-medium mb-1">
              {{ ProductList.title }}
            </h1>
            <div class="flex mb-4">
              <span class="flex items-center">
                <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                  stroke-width="2" class="w-4 h-4 text-red-500" viewBox="0 0 24 24">
                  <path
                    d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z">
                  </path>
                </svg>
                <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                  stroke-width="2" class="w-4 h-4 text-red-500" viewBox="0 0 24 24">
                  <path
                    d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z">
                  </path>
                </svg>
                <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                  stroke-width="2" class="w-4 h-4 text-red-500" viewBox="0 0 24 24">
                  <path
                    d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z">
                  </path>
                </svg>
                <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                  stroke-width="2" class="w-4 h-4 text-red-500" viewBox="0 0 24 24">
                  <path
                    d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z">
                  </path>
                </svg>
                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  class="w-4 h-4 text-red-500" viewBox="0 0 24 24">
                  <path
                    d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z">
                  </path>
                </svg>
                <span class="text-gray-600 ml-3">4 Reviews</span>
              </span>
              <span class="flex ml-3 pl-3 py-2 border-l-2 border-gray-200">
                <a class="text-gray-500">
                  <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    class="w-5 h-5" viewBox="0 0 24 24">
                    <path d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"></path>
                  </svg>
                </a>
                <a class="ml-2 text-gray-500">
                  <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    class="w-5 h-5" viewBox="0 0 24 24">
                    <path
                      d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z">
                    </path>
                  </svg>
                </a>
                <a class="ml-2 text-gray-500">
                  <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    class="w-5 h-5" viewBox="0 0 24 24">
                    <path
                      d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z">
                    </path>
                  </svg>
                </a>
              </span>
            </div>
            <form class="mt-10">
              <!-- Colors -->
              <div>
                <h3 class="text-sm font-medium text-gray-900">Color</h3>

                <fieldset class="mt-4">
                  <legend class="sr-only">Choose a color</legend>
                  <div class="flex items-center space-x-3">
                    <!--
                  Active and Checked: "ring ring-offset-1"
                  Not Active and Checked: "ring-2"
                -->
                    <label class="
                        -m-0.5
                        relative
                        p-0.5
                        rounded-full
                        flex
                        items-center
                        justify-center
                        cursor-pointer
                        focus:outline-none
                        ring-gray-400
                      ">
                      <input type="radio" name="color-choice" value="White" class="sr-only"
                        aria-labelledby="color-choice-0-label" />
                      <span id="color-choice-0-label" class="sr-only">
                        White
                      </span>
                      <span aria-hidden="true" class="
                          h-8
                          w-8
                          bg-white
                          border border-black border-opacity-10
                          rounded-full
                        "></span>
                    </label>

                    <!--
                  Active and Checked: "ring ring-offset-1"
                  Not Active and Checked: "ring-2"
                -->
                    <label class="
                        -m-0.5
                        relative
                        p-0.5
                        rounded-full
                        flex
                        items-center
                        justify-center
                        cursor-pointer
                        focus:outline-none
                        ring-gray-400
                      ">
                      <input type="radio" name="color-choice" value="Gray" class="sr-only"
                        aria-labelledby="color-choice-1-label" />
                      <span id="color-choice-1-label" class="sr-only">
                        Gray
                      </span>
                      <span aria-hidden="true" class="
                          h-8
                          w-8
                          bg-gray-200
                          border border-black border-opacity-10
                          rounded-full
                        "></span>
                    </label>

                    <!--
                  Active and Checked: "ring ring-offset-1"
                  Not Active and Checked: "ring-2"
                -->
                    <label class="
                        -m-0.5
                        relative
                        p-0.5
                        rounded-full
                        flex
                        items-center
                        justify-center
                        cursor-pointer
                        focus:outline-none
                        ring-gray-900
                      ">
                      <input type="radio" name="color-choice" value="Black" class="sr-only"
                        aria-labelledby="color-choice-2-label" />
                      <span id="color-choice-2-label" class="sr-only">
                        Black
                      </span>
                      <span aria-hidden="true" class="
                          h-8
                          w-8
                          bg-gray-900
                          border border-black border-opacity-10
                          rounded-full
                        "></span>
                    </label>
                  </div>
                </fieldset>
              </div>

              <!-- Sizes -->
              <div class="mt-10">
                <div class="flex items-center justify-between">
                  <h3 class="text-sm font-medium text-gray-900">Size</h3>
                  <a href="#" class="
                      text-sm
                      font-medium
                      text-indigo-600
                      hover:text-indigo-500
                    ">Size guide</a>
                </div>

                <fieldset class="mt-4">
                  <legend class="sr-only">Choose a size</legend>
                  <div class="flex gap-2">
                    <label class="
                        group
                        relative
                        border
                        rounded-md
                        w-2
                        h-2
                        py-2
                        px-4
                        flex
                        items-center
                        justify-center
                        text-sm
                        font-medium
                        uppercase
                        hover:bg-gray-50
                        focus:outline-none
                        sm:flex-1 sm:py-6
                        bg-gray-50
                        text-gray-200
                        cursor-not-allowed
                      ">
                      <input type="radio" name="size-choice" value="XXS" disabled class="sr-only"
                        aria-labelledby="size-choice-0-label" />
                      <span id="size-choice-0-label">XXS</span>

                      <span aria-hidden="true" class="
                          pointer-events-none
                          absolute
                          -inset-px
                          rounded-md
                          border-2 border-gray-200
                        ">
                        <svg class="
                            absolute
                            inset-0
                            h-full
                            w-full
                            stroke-2
                            text-gray-200
                          " viewBox="0 0 100 100" preserveAspectRatio="none" stroke="currentColor">
                          <line x1="0" y1="100" x2="100" y2="0" vector-effect="non-scaling-stroke" />
                        </svg>
                      </span>
                    </label>
                    <label class="
                        group
                        relative
                        border
                        rounded-md
                        w-2
                        h-2
                        py-2
                        px-4
                        flex
                        items-center
                        justify-center
                        text-sm
                        font-medium
                        uppercase
                        hover:bg-gray-50
                        focus:outline-none
                        sm:flex-1 sm:py-6
                        bg-white
                        shadow-sm
                        text-gray-900
                        cursor-pointer
                      ">
                      <input type="radio" name="size-choice" value="XS" class="sr-only"
                        aria-labelledby="size-choice-1-label" />
                      <span id="size-choice-1-label">XS</span>
                      <span class="
                          pointer-events-none
                          absolute
                          -inset-px
                          rounded-md
                        " aria-hidden="true"></span>
                    </label>
                  </div>
                </fieldset>
              </div>
              <div class="flex gap-4">
                <button type="submit" class="
                    flex-1
                    w-full
                    items-center
                    justify-center
                    rounded-md
                    border border-transparent
                    bg-indigo-600
                    py-3
                    px-8
                    text-base
                    font-medium
                    text-white
                    hover:bg-indigo-700
                    focus:outline-none
                    focus:ring-2
                    focus:ring-indigo-500
                    focus:ring-offset-2
                  ">
                  buynow
                </button>
                <button type="submit" class="
                    flex-1
                    w-full
                    items-center
                    justify-center
                    rounded-md
                    border border-transparent
                    bg-indigo-600
                    py-3
                    px-8
                    text-base
                    font-medium
                    text-white
                    hover:bg-indigo-700
                    focus:outline-none
                    focus:ring-2
                    focus:ring-indigo-500
                    focus:ring-offset-2
                  ">
                  addtocart
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>
    <section>
      <span class="sr-only">Product Detail</span>
      <div class="container mx-auto">
        <div class="lg:w-4/5 mx-auto">
          <p class="px-2 py-3">product detail - {{ ProductList.title }}</p>
          {{ descMore }}
          <div :class="!descMore ? 'max-h-[1000px] overflow-hidden' : ''">
            <p>{{ ProductList.description }}</p>
            <img :src="im" alt="" class="w-full" srcset="" v-for="(im, i) in ProductList.images" :key="i" />
          </div>

          <div class="text-center px-2">
            <button class="
                px-3
                py-2
                rounded-md
                border border-transparent
                bg-indigo-600
              " @click="descMore = !descMore">
              {{ descMore ? "View Less" : "View More" }}
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>