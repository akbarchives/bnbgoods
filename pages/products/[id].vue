<template>
  <div class="mx-auto w-full max-w-screen-2xl pb-20 pt-10">
    <div class="flex w-full flex-wrap px-6 sm:px-8">
      <!-- BreadCrumbs -->
      <div class="mb-6 flex gap-4 text-lg font-medium text-slate-600">
        <NuxtLink
          to="/"
          class="hover:text-black"
          >Home</NuxtLink
        >
        \
        <NuxtLink
          to="/products"
          class="hover:text-black"
          >Products</NuxtLink
        >
        \
        <span class="font-bold text-black"> {{ product.title }}</span>
      </div>
      <!-- Image Display -->
      <div class="w-full">
        <!-- Galleries content goes here -->
        <ImageDisplay
          class="mt-6 w-full lg:h-96"
          :thumbnail="product.images[0]"
          :img1="product.images[1] ? product.images[1] : product.images[0]"
          :img2="product.images[2] ? product.images[2] : product.images[0]"
          :img3="product.images[3] ? product.images[3] : product.images[0]"
          :img4="product.images[4] ? product.images[4] : product.images[0]"
        />
      </div>

      <!-- details -->
      <div class="mt-12 w-full">
        <div class="flex gap-8">
          <!-- Section Details -->
          <div class="h-[1200px] basis-auto sm:basis-2/3">
            <!-- Section details content goes here -->

            <div class="flex h-[400px] flex-col justify-between">
              <div>
                <!-- product main detail  -->
                <div class="flex justify-between">
                  <div class="flex flex-col">
                    <h1 class="text-lg font-semibold text-slate-600">
                      {{ product.brand }}
                    </h1>
                    <h1 class="text-2xl font-bold">{{ product.title }}</h1>
                  </div>
                  <div class="text-2xl font-bold">
                    <h2 class="text-2xl font-semibold">
                      ${{
                        product.price -
                        (product.price * product.discountPercentage) / 100
                      }}
                    </h2>
                    <div class="flex justify-end">
                      <h2
                        class="mr-2 rounded bg-red-400 px-1 text-base font-medium text-white"
                      >
                        {{ Math.floor(product.discountPercentage) }}%
                      </h2>
                      <h2 class="text-base font-medium line-through">
                        ${{ product.price }}
                      </h2>
                    </div>
                  </div>
                </div>

                <!-- rating and stock -->
                <div class="flex items-center gap-2">
                  <h2>
                    Rating
                    <span class="text-lg text-yellow-400">&#9733;</span>
                    <span class="font-semibold">{{ product.rating }}</span>
                  </h2>
                  <h2>•</h2>
                  <h2>
                    Stock
                    <span class="font-semibold">({{ product.stock }})</span>
                  </h2>
                </div>
                <!-- description -->
                <div>
                  <div class="mt-6">
                    <h2 class="text-lg font-semibold">Description :</h2>
                  </div>
                  <div class="mt-2">
                    <h2 class="w-2/3">{{ product.description }}</h2>
                  </div>
                </div>
              </div>
              <!-- category -->
              <div class="flex items-center justify-between">
                <NuxtLink
                  :to="`/categories/${product.category}`"
                  class="w-fit rounded-2xl border px-4 py-2 font-semibold text-black hover:bg-slate-100"
                >
                  #{{ product.category }}
                </NuxtLink>

                <div>
                  <NuxtLink
                    to="/"
                    class="rounded-md p-2 hover:bg-slate-100"
                    ><ArrowUpOnSquareIcon
                      class="inline-block h-6 w-6 align-middle"
                    />
                    <span class="pl-2">Share</span></NuxtLink
                  >
                  <NuxtLink
                    to="/"
                    class="rounded-md p-2 hover:bg-slate-100"
                    ><HeartIcon
                      class="inline-block h-6 w-6 align-middle"
                    /><span class="pl-2">Save</span></NuxtLink
                  >
                </div>
              </div>
            </div>
            <!-- review dan rating -->
            <div class="mt-8 flex flex-col border-t">
              <div class="mt-6">
                <h2 class="text-xl font-semibold">
                  Buyers Review
                  <span class="text-slate-600">(29 Reviews)</span>
                </h2>
              </div>

              <!-- review 1 -->
              <div class="border-b pb-2">
                <div class="mt-6">
                  <span class="text-lg text-yellow-400">
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                  </span>
                  2 days ago
                </div>

                <div class="flex flex-row items-start">
                  <UserCircleIcon
                    class="mr-2 h-20 w-20 basis-auto text-slate-400"
                  />
                  <div class="flex flex-col">
                    <h1 class="text-lg font-semibold">Lita</h1>
                    <h1>
                      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                      Optio tempore nesciunt, labore architecto possimus qui
                      quod beatae illo a maiores!
                    </h1>
                  </div>
                </div>
              </div>
              <!-- review 2 -->
              <div class="border-b pb-2">
                <div class="mt-6">
                  <span class="text-lg text-yellow-400">
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                  </span>
                  3 days ago
                </div>

                <div class="flex flex-row items-start">
                  <UserCircleIcon
                    class="mr-2 h-20 w-20 basis-auto text-slate-400"
                  />
                  <div class="flex flex-col">
                    <h1 class="text-lg font-semibold">Jeremy</h1>
                    <h1>
                      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                      Optio tempore nesciunt, labore architecto possimus qui
                      quod beatae illo a maiores!
                    </h1>
                  </div>
                </div>
              </div>
              <!-- review 3 -->
              <div class="border-b pb-2">
                <div class="mt-6">
                  <span class="text-lg text-yellow-400">
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                    <StarIcon class="inline-block h-4 w-4" />
                  </span>
                  3 days ago
                </div>

                <div class="flex flex-row items-start">
                  <UserCircleIcon
                    class="mr-2 h-20 w-20 basis-auto text-slate-400"
                  />
                  <div class="flex flex-col">
                    <h1 class="text-lg font-semibold">Aldo</h1>
                    <h1>
                      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                      Optio tempore nesciunt, labore architecto possimus qui
                      quod beatae illo a maiores!
                    </h1>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Sticky Cart -->
          <div
            class="sticky top-32 hidden h-[400px] flex-auto basis-1/3 sm:block"
          >
            <!-- Cart content goes here -->
            <div
              class="flex h-96 w-full flex-col rounded-2xl border border-slate-400 bg-slate-50 p-6"
            >
              <div class="mb-6">
                <ShoppingCartIcon
                  class="text-primary inline-block h-8 w-8 align-middle"
                /><span class="pl-2 text-xl font-semibold">Cart</span>
              </div>

              <!-- cart list -->
              <div class="flex w-full flex-row pt-2">
                <div class="basis-auto">
                  <img
                    class="h-16 w-16 rounded-lg object-cover"
                    :src="product.thumbnail"
                    alt=""
                  />
                </div>
                <div class="flex basis-3/4 flex-col pl-2">
                  <h1 class="text-lg font-semibold">{{ product.title }}</h1>
                  <div class="flex h-full items-center">
                    <div class="flex w-fit overflow-hidden rounded-lg border">
                      <button
                        class="bg-red-400 px-2 font-bold text-white"
                        @click="decrement"
                      >
                        -
                      </button>
                      <input
                        class="w-10 text-center"
                        type="number"
                        v-model.number="quantity"
                        min="0"
                      />
                      <button
                        class="bg-red-400 px-2 font-bold text-white"
                        @click="increment"
                      >
                        +
                      </button>
                    </div>
                    <h2 class="w-1/2 pl-2 font-semibold">
                      Stock ({{ product.stock }})
                    </h2>
                  </div>
                </div>
                <!-- <div class="bg mx-auto basis-auto self-center">
                  <TrashIcon class="text-primary h-8 w-8" />
                </div> -->
              </div>
              <!-- addition -->
              <p class="pt-2 text-base font-semibold">
                Total Price: $
                {{
                  quantity *
                  (product.price -
                    (product.price * product.discountPercentage) / 100)
                }}
              </p>
              <!-- CTA -->
              <div class="flex h-full flex-auto flex-col justify-end">
                <button
                  class="my-2 w-full rounded-lg border border-red-400 bg-red-100 p-2 font-semibold duration-200 hover:bg-white"
                >
                  add to cart
                </button>
                <button
                  class="w-full rounded-lg bg-red-400 p-2 font-semibold text-white duration-200 hover:bg-red-500"
                >
                  Buy Now
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {
  UserCircleIcon,
  StarIcon,
  ShoppingCartIcon,
  TrashIcon,
} from '@heroicons/vue/24/solid';

export default {
  components: {
    StarIcon,
    UserCircleIcon,
    ShoppingCartIcon,
    TrashIcon,
  },
  data() {
    return {
      quantity: 1,
    };
  },
  computed: {
    totalPrice() {
      return this.quantity * this.price;
    },
  },
  methods: {
    increment() {
      this.quantity++;
    },
    decrement() {
      if (this.quantity > 0) {
        this.quantity--;
      }
    },
  },
};
</script>

<script setup>
import { ArrowUpOnSquareIcon, HeartIcon } from '@heroicons/vue/24/outline';
import { AdjustmentsHorizontalIcon } from '@heroicons/vue/24/solid';
const layout = 'details';
const route = useRoute();
console.log(route.params.id);

// const id = route.params.id;
// const product = products[id - 1];

const { data: product } = await useFetch(
  'https://dummyjson.com/products/' + route.params.id
);

console.log(product);
</script>

<!-- <style>
  div {
    color: #f5e5e8;
  }
  </style> -->
