<template>
  <div
    class="custom-container mx-auto mb-10 max-w-screen-2xl px-6 py-10 sm:px-8"
  >
    <h1 class="mb-2 mt-12 text-3xl font-semibold">Hot Products 🔥</h1>

    <h1 class="mb-4 text-xl font-normal md:w-1/2">
      Product on sale with high quality
    </h1>

    <!-- card 6 -->
    <div
      class="pt-12"
      v-if="pending"
    >
      <div class="mb-6 grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-6">
        <CardSkeleton
          v-for="index in 6"
          :key="index"
        />
      </div>
    </div>
    <div v-else>
      <div class="grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-6">
        <NuxtLink
          v-for="card in hotProducts"
          :to="`/products/${card.id}`"
          :key="card.id"
        >
          <CardSwipe
            :title="card.title"
            :thumbnail="card.thumbnail"
            :category="card.category"
            :description="card.description"
            :discountPercentage="card.discountPercentage"
            :price="card.price"
            :rating="card.rating"
            :img1="card.images[0]"
            :img2="card.images[1]"
            :img3="card.images[2]"
            :img4="card.images[3]"
          />
        </NuxtLink>
      </div>
    </div>

    <h1 class="mb-2 mt-12 text-3xl font-semibold">Watches</h1>
    <h1 class="mb-4 text-xl font-normal">
      Experience Luxury Craftsmanship on Your Wrist
    </h1>

    <!-- Card 4 -->
    <div
      class="pt-12"
      v-if="pending"
    >
      <div class="mb-6 grid grid-cols-2 gap-4 sm:grid-cols-4 lg:grid-cols-4">
        <CardSkeleton
          v-for="index in 8"
          :key="index"
        />
      </div>
    </div>
    <div v-else>
      <div class="grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-4">
        <NuxtLink
          v-for="card in watchesProducts"
          :to="`/products/${card.id}`"
          :key="card.id"
        >
          <CardSwipe
            :title="card.title"
            :thumbnail="card.thumbnail"
            :category="card.category"
            :description="card.description"
            :discountPercentage="card.discountPercentage"
            :price="card.price"
            :rating="card.rating"
            :img1="card.images[0]"
            :img2="card.images[1]"
            :img3="card.images[2]"
            :img4="card.images[3]"
          />
        </NuxtLink>
      </div>
    </div>

    <h1 class="mb-2 mt-12 text-3xl font-semibold">Smartphones</h1>
    <h1 class="mb-4 text-xl font-normal">
      Stay Connected and Inspired with Our Innovative Smartphones
    </h1>

    <!-- Card 6 -->
    <div
      class="pt-12"
      v-if="pending"
    >
      <div class="mb-6 grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-6">
        <CardSkeleton
          v-for="index in 6"
          :key="index"
        />
      </div>
    </div>
    <div v-else>
      <div class="grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-6">
        <NuxtLink
          v-for="card in smartphonesProducts"
          :to="`/products/${card.id}`"
          :key="card.id"
        >
          <CardSwipe
            :title="card.title"
            :thumbnail="card.thumbnail"
            :category="card.category"
            :description="card.description"
            :discountPercentage="card.discountPercentage"
            :price="card.price"
            :rating="card.rating"
            :img1="card.images[0]"
            :img2="card.images[1]"
            :img3="card.images[2]"
            :img4="card.images[3]"
          />
        </NuxtLink>
      </div>
    </div>

    <h1 class="mb-2 mt-12 text-3xl font-semibold">Fragrances</h1>

    <h1 class="mb-4 text-xl font-normal md:w-1/2">
      Enchanting Fragrances for Unforgettable Moments
    </h1>
    <!-- card 3 -->
    <div
      class="pt-12"
      v-if="pending"
    >
      <div class="mb-6 grid grid-cols-2 gap-4 sm:grid-cols-3">
        <CardSkeleton
          v-for="index in 4"
          :key="index"
        />
      </div>
    </div>
    <div v-else>
      <div class="grid grid-cols-1 gap-4 sm:grid-cols-4">
        <NuxtLink
          v-for="card in fragrancesProducts"
          :to="`/products/${card.id}`"
          :key="card.id"
        >
          <CardSwipe
            :title="card.title"
            :thumbnail="card.thumbnail"
            :category="card.category"
            :description="card.description"
            :discountPercentage="card.discountPercentage"
            :price="card.price"
            :rating="card.rating"
            :img1="card.images[0]"
            :img2="card.images[1]"
            :img3="card.images[2]"
            :img4="card.images[3]"
          />
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      pending: true,
      hotProducts: null,
      fragrancesProducts: null,
      watchesProducts: null,
      smartphonesProducts: null,
    };
  },
  methods: {
    setHotProducts(data) {
      this.hotProducts = data;
    },
    setFragrancesProducts(data) {
      this.fragrancesProducts = data;
    },
    setSmartphonesProducts(data) {
      this.smartphonesProducts = data;
    },
    setWatchesProducts(data) {
      this.watchesProducts = data;
    },
  },
  mounted() {
    axios
      .get('https://dummyjson.com/products?limit=100')
      .then(response => {
        const products = response.data.products; // Assuming the products are returned in the `data` property

        const sortedProducts = products.sort(
          (a, b) => b.discountPercentage - a.discountPercentage
        );

        this.setHotProducts(sortedProducts.slice(0, 6));
        this.pending = false; // Update pending state after successful request
      })
      .catch(error => {
        console.log('Gagal :', error);
        this.pending = false; // Update pending state even if there's an error
      });
    axios
      .get('https://dummyjson.com/products/search?q=watch')
      .then(response => {
        this.setWatchesProducts(response.data.products.slice(0, 8));
        this.pending = false; // Update pending state after successful request
      })
      .catch(error => {
        console.log('Gagal :', error);
        this.pending = false; // Update pending state even if there's an error
      });
    axios
      .get('https://dummyjson.com/products/category/fragrances')
      .then(response => {
        this.setFragrancesProducts(response.data.products.slice(0, 4));
        this.pending = false; // Update pending state after successful request
      })
      .catch(error => {
        console.log('Gagal :', error);
        this.pending = false; // Update pending state even if there's an error
      });
    axios
      .get('https://dummyjson.com/products/category/smartphones')
      .then(response => {
        this.setSmartphonesProducts(response.data.products.slice(0, 6));
        this.pending = false; // Update pending state after successful request
      })
      .catch(error => {
        console.log('Gagal :', error);
        this.pending = false; // Update pending state even if there's an error
      });
  },
};

// const { data: products } = useFetch('https://fakestoreapi.com/products');
// console.log(products);

// const { data: movie } = useFetch(
//   'https://api.themoviedb.org/3/movie/popular?api_key=35d428792ace5959fdc3f64e2ecc08b6'
// );
// console.log(movie);
</script>
