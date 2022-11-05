<template>
    <swiper :slidesPerView="4" :spaceBetween="30" :centeredSlides="true" :pagination="{
        clickable: true,
    }" :modules="modules" class="mySwiper">
        <swiper-slide>
            <div class="justify-center px-3 py-3 bg-neutral-200 rounded-xl" v-for="(ix, i) in cateGory" :key="i">
                <img :src="'/category/' + ix + '.png'" class="w-12" alt="" srcset="" />
                <p class="text-[14px]">{{ ix }}</p>
            </div>
        </swiper-slide>
    </swiper>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";

// import required modules
import { Pagination } from "swiper";

export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    setup() {
        return {
            modules: [Pagination],
        };
    },
};
</script>
  