<template>
  <div>this is category index</div>
  <!-- <div v-for="c in categories">
    {{ c }}
  </div> -->

  <nuxt-link
    v-for="c in categories"
    :to="`/categories/${c}`"
    >{{ c }}
  </nuxt-link>
</template>

<script setup>
const { data: categories } = await useFetch(
  'https://dummyjson.com/products/categories'
);

console.log(categories);
</script>
