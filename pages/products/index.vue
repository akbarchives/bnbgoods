<template>
  <div
    class="custom-container mx-auto mb-10 max-w-screen-2xl px-6 py-10 sm:px-8"
  >
    <!-- <NuxtLink to="/categories">categories</NuxtLink> -->
    <h1 class="mb-6 mt-12 text-3xl font-semibold">All Products</h1>

    <!-- <h1 class="mb-4 text-xl font-normal md:w-1/2">
      Product on sale with high quality
    </h1> -->

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
          v-for="card in products"
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
      products: null,
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get('https://dummyjson.com/products/')
      .then(response => {
        const products = response.data.products; // Assuming the products are returned in the `data` property
        this.setProducts(products);
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
