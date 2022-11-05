<template>
  <swiper :pagination="true" :modules="modules" class="mySwiper">
    <swiper-slide>
      <div class="rounded">
        <img src="https://icms-image.slatic.net/images/ims-web/f47b9e3a-27ca-4c43-b516-d6be3625f3bc.jpg"
          class="w-[100%]" />
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
  