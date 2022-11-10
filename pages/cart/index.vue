<script setup>
/// https://dummyjson.com/carts/user/5

const CartList = await $fetch(`https://dummyjson.com/carts/user/5`);
</script>
<template>
    <div>
        <section class="text-gray-700 body-font overflow-hidden bg-white">
            <div class="container py-24 mx-auto">
                <div class="lg:w-4/5 mx-auto flex flex-wrap">
                    <div class="flex">
                        <div class="flex-11 gap-y-2">
                            <!-- {{ CartList }} -->
                            <div v-for="(ic, i) in CartList.carts" :key="i">
                                <div v-for="(is, ix) in ic.products" :key="ix" class="flex">
                                    <div class="w-[80px] h-[80px]">
                                        <img src="https://lzd-img-global.slatic.net/g/p/b097644531ac7389c56a6cfd3a85b695.jpg_2200x2200q80.jpg_.webp"
                                            alt="" class="rounded-xl w-[80px] h-[80px]" srcset="" />
                                    </div>
                                    <div class="w-full">
                                        <p class="px-2 text-sm">{{ is.title }}</p>
                                    </div>
                                    <div class="w-full">
                                        <p class="px-2 text-sm">{{ is.price * 100 }}</p>
                                    </div>
                                    <div class="flex border rounded-xl h-[35px]">
                                        <button class="px-2 h-full w-8 rounded-xl border">-</button><input type="text"
                                            value="0" class="text-center w-[50px]" /><button
                                            class="px-2 h-full w-8 rounded-xl border">
                                            +
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="relative">
                            <h1 class="text-xl">Order Summary</h1>
                            <div class="flex justify-between text-base font-medium text-gray-900">
                                <h3>Subtotal (10 items)</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <div class="flex justify-between text-base font-medium text-gray-900">
                                <h3>Subtotal (10 items)</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <div>
                                <input type="text" class="px-3 py-2 border" placeholder="Voucher Code" /><button
                                    class="px-4 py-2 border">Apply</button>
                            </div>
                            <div class="flex justify-between text-base font-medium text-gray-900">
                                <h3>Total</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <button class="w-full bg-blue-100 py-2">Process Order</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>