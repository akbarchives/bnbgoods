<template>
  <div class="h-64 select-none overflow-hidden rounded-lg border sm:hidden">
    <swiper
      :loop="true"
      :pagination="{
        clickable: true,
      }"
      :modules="modules"
      class="mySwiper h-full"
    >
      <swiper-slide class="h-full">
        <img
          class="h-full w-full object-cover object-left-top"
          :src="thumbnail"
          alt=""
        />
      </swiper-slide>
      <swiper-slide class="h-full">
        <img
          class="h-full w-full object-cover object-left-top"
          :src="img1"
          alt=""
        />
      </swiper-slide>
      <swiper-slide class="h-full">
        <img
          class="h-full w-full object-cover object-left-top"
          :src="img2"
          alt=""
        />
      </swiper-slide>
      <swiper-slide class="h-full">
        <img
          class="h-full w-full object-cover object-left-top"
          :src="img3"
          alt=""
        />
      </swiper-slide>
      <swiper-slide class="h-full">
        <img
          class="h-full w-full object-cover object-left-top"
          :src="img4 ? img4 : thumbnail"
          alt=""
        />
      </swiper-slide>
    </swiper>
  </div>
  <!-- screen sm to lg -->
  <div
    class="hidden h-[300px] w-full gap-2 overflow-hidden rounded-2xl border sm:grid sm:grid-flow-col sm:grid-rows-2"
  >
    <div class="col-span-2 row-span-2 overflow-hidden">
      <img
        class="h-full w-full object-cover object-left-top transition-all duration-500 ease-in-out hover:scale-105 hover:brightness-[90%]"
        :src="thumbnail"
        alt=""
      />
    </div>

    <div class="overflow-hidden">
      <img
        class="h-full w-full object-cover object-center transition-all duration-500 ease-in-out hover:scale-105 hover:brightness-[90%]"
        :src="img1"
        alt=""
      />
    </div>
    <div class="overflow-hidden">
      <img
        class="h-full w-full object-cover object-center transition-all duration-500 ease-in-out hover:scale-105 hover:brightness-[90%]"
        :src="img2"
        alt=""
      />
    </div>
    <div class="overflow-hidden">
      <img
        class="h-full w-full object-cover object-center transition-all duration-500 ease-in-out hover:scale-105 hover:brightness-[90%]"
        :src="img3"
        alt=""
      />
    </div>
    <div class="overflow-hidden">
      <img
        class="h-full w-full object-cover object-center transition-all duration-500 ease-in-out hover:scale-105 hover:brightness-[90%]"
        :src="img4"
        alt=""
      />
    </div>
  </div>
</template>

<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import 'swiper/css/pagination';

// import required modules
import { Pagination } from 'swiper';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    thumbnail: String,
    img1: String,
    img2: String,
    img3: String,
    img4: String,
  },
  setup() {
    return {
      modules: [Pagination],
    };
  },
};
</script>
<style>
img {
  filter: grayscale(30%);
}
img:hover {
  filter: grayscale(0%);
}
</style>
