<script setup>
import { ref } from "vue";
import { RadioGroup, RadioGroupLabel, RadioGroupOption } from "@headlessui/vue";
const route = useRoute();
const router = useRouter();
const CartList = await $fetch(`https://dummyjson.com/carts/user/5`);

const handleProcess = () => {
    router.push(
        "/cart?sto=payment.c000&by=12a12sd1f2a1sf2a1f2a1f2asfa1s21a2sfd1a2s"
    );
};
const plan = ref("TUP");
</script>
<template>
    <div>
        <section class="text-gray-700 body-font overflow-hidden bg-white">
            <div class="container py-10 mx-auto">
                <div class="flex relative">
                    <div class="w-3/4 lg:pr-10">
                        <RadioGroup v-model="plan">
                            <RadioGroupLabel>ເລືອກຊ່ອງທາງການຊຳລະເງິນ</RadioGroupLabel>
                            <RadioGroupOption as="div" v-slot="{ checked }" value="COD">
                                <span :class="checked ? 'bg-blue-200' : ''">ເກັບປາຍທາງ</span>
                            </RadioGroupOption>
                            <RadioGroupOption as="div" v-slot="{ checked }" value="TUP">
                                <span :class="checked ? 'bg-blue-200' : ''">ຊຳລະຜ່ານ App Banking</span>
                            </RadioGroupOption>
                            <RadioGroupOption as="div" v-slot="{ checked }" value="FRP">
                                <span :class="checked ? 'bg-blue-200' : ''">ໂອນເງິນຜ່ານທະນາຄານ</span>
                            </RadioGroupOption>
                        </RadioGroup>
                        <ClientOnly>
                            <div class="bip flex gap-2">
                                <div v-if="plan == 'TUP'" class="flex px-2 py-2 rounded bg-red-100 items-center">
                                    <img src="/payment/bcel-one.png" class="w-9 h-9" alt="" srcset="" />
                                    <div>
                                        <p class="pl-2 text-md">ກົດເພື່ອຊຳລະເງິນ</p>
                                        <p class="pl-2 text-sm">BCEL One</p>
                                    </div>
                                </div>
                                <div v-if="plan == 'TUP'" class="flex px-2 py-2 rounded bg-[#2a357c] text-white items-center">
                                    <img src="/payment/sthub.webp" class="w-9 h-9" alt="" srcset="" />
                                    <div>
                                        <p class="pl-2 text-md">ກົດເພື່ອຊຳລະເງິນ</p>
                                        <p class="pl-2 text-sm">ST HUB</p>
                                    </div>
                                </div>
                                <div v-if="plan == 'TUP'" class="flex px-2 py-2 rounded bg-[#1883c9] items-center text-white">
                                    <img src="/payment/ldbtrush.webp" class="w-9 h-9" alt="" srcset="" />
                                    <div>
                                        <p class="pl-2 text-md">ກົດເພື່ອຊຳລະເງິນ</p>
                                        <p class="pl-2 text-sm">LDB Trush</p>
                                    </div>
                                </div>
                            </div>
                        </ClientOnly>

                    </div>
                    <div class="w-3/4 lg:pr-10" v-if="!route.query.sto">
                        <!-- {{ CartList }} -->
                        <div v-for="(ic, i) in CartList.carts" :key="i" class="border px-2 rounded-xl py-2 mt-5">
                            <div class="flex py-2">
                                <IconsStore class="w-6" />
                                <p class="pl-2 text-[14px]">SHOP 1</p>
                            </div>
                            <div v-for="(is, ix) in ic.products" :key="ix"
                                class="flex border mt-1 py-2 px-2 rounded-xl">
                                <div class="flex-none w-[80px] h-[80px]">
                                    <img src="https://lzd-img-global.slatic.net/g/p/b097644531ac7389c56a6cfd3a85b695.jpg_2200x2200q80.jpg_.webp"
                                        alt="" class="rounded-xl" srcset="" />
                                </div>
                                <div class="max-w-[500px] pl-2">
                                    <p class="text-[14px]">
                                        item RoRo ชั้นวางของ 4 ชั้น ชั้นวางเครื่องปรุง มี 2 แบบ
                                        ชั้นเอนกประสงค์รับน้ำหนักได้ถึง 50 กิโล แข็งแรง ทนทาน
                                    </p>
                                    <p class="text-[10pt]">No Brand,Color: ສີຟ້າ</p>
                                    <div>
                                        <span class="rounded-3xl bg-red-400 px-4 text-[8pt]">Buy 2, Save
                                            ฿10.00</span><span class="text-[8pt] pl-3">Only 5 item(s) in stock</span>
                                    </div>
                                </div>
                                <div class="flex-1 w-[20%] text-center">
                                    <p class="px-2 text-sm">{{ is.price * 100 }}</p>
                                </div>
                                <div>
                                    <p class="text-sm">ຈຳນວນ</p>
                                    <div class="flex-2 border border-red-700 rounded-xl h-[35px]">
                                        <button class="
                        px-2
                        h-full
                        w-8
                        rounded-xl
                        border
                        bg-red-700
                        text-white
                      ">
                                            -</button><input type="text" value="0"
                                            class="text-center w-[50px]" /><button class="
                        px-2
                        h-full
                        w-8
                        rounded-xl
                        border
                        bg-red-700
                        text-white
                      ">
                                            +
                                        </button>
                                    </div>
                                </div>
                            </div>
                            <div class="intro-y block sm:flex items-center h-10">
                                <h2 class="text-lg font-medium truncate mr-5"></h2>
                                <div class="flex items-center sm:ml-auto mt-3 sm:mt-0">
                                    <p class="text-[14px] float-right clear-right">
                                        ຈຳນວນ: (5) | 2000000 ກີບ
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="flex-1 w-1/4 sticky top-0">
                        <div></div>
                        <span class="sr-only">order infomation</span>
                        <div class="relative my-2">
                            <h1 class="text-md py-2">Shiping</h1>
                            <!-- <ShipingNone /> -->
                            <ShipingItem />
                        </div>
                        <div class="relative my-2">
                            <h1 class="text-md py-2">Order Summary</h1>
                            <div class="
                  flex
                  justify-between
                  text-base
                  font-medium
                  text-gray-900
                  py-1
                ">
                                <h3 class="text-sm">Subtotal (10 items)</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <div class="
                  flex
                  justify-between
                  text-base
                  font-medium
                  text-gray-900
                  py-1
                ">
                                <h3 class="text-sm">ອາກອນ</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <div class="
                  flex
                  justify-between
                  text-base
                  font-medium
                  text-gray-900
                  py-1
                ">
                                <h3 class="text-sm">ຄ່າຂົນສົ່ງ</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <div class="py-3 flex">
                                <input type="text" class="px-3 py-2 border border-red-700 w-full"
                                    placeholder="Voucher Code" /><button class="px-4 py-2 border bg-red-700 text-white">
                                    Apply
                                </button>
                            </div>
                            <div class="
                  flex
                  justify-between
                  text-base
                  font-medium
                  text-gray-900
                  py-1
                ">
                                <h3 class="text-sm">Total</h3>
                                <p class="ml-4">$90.00</p>
                            </div>
                            <button @click="handleProcess" class="w-full py-2 my-3 rounded-xl bg-red-700 text-white">
                                Process Order
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>