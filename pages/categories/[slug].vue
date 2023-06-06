<template>
  <div
    class="custom-container mx-auto mb-10 max-w-screen-2xl px-6 py-10 sm:px-8"
  >
    <!-- <NuxtLink to="/categories">categories</NuxtLink> -->
    <h1 class="my-12 text-3xl font-semibold">Category: {{ title }}</h1>

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
          v-for="card in posts.products"
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

<script setup>
const route = useRoute();
const title = route.params.slug;

const { data: posts } = await useFetch(
  'https://dummyjson.com/products/category/' + route.params.slug
);

console.log(posts);
</script>
