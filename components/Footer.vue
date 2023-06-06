<template>
  <div class="border-y">
    <div class="mx-auto max-w-screen-2xl bg-white">
      <!-- mobile display -->
      <div
        class="fixed bottom-0 z-50 flex w-full flex-row justify-center gap-12 border-t bg-white px-8 py-3 text-slate-400 sm:hidden"
      >
        <a
          href=""
          class="flex flex-col"
        >
          <MagnifyingGlassIcon class="mx-auto h-8 w-8" />
          <p class="text-xs">Search</p>
        </a>
        <a
          href=""
          class="flex flex-col"
        >
          <HeartIcon class="mx-auto h-8 w-8" />
          <p class="text-xs">Whislists</p>
        </a>
        <a
          href=""
          class="flex flex-col"
        >
          <UserIcon class="mx-auto h-8 w-8" />
          <p class="text-xs">Log in</p>
        </a>
      </div>

      <!-- dekstop display -->

      <div
        class="fixed bottom-0 hidden w-full flex-row justify-between border-t bg-white px-8 py-3 sm:flex"
      >
        <!-- left footer-->
        <div
          class="flex flex-row flex-wrap items-center gap-2 text-xs lg:text-base"
        >
          <p>© 2023 Airbnb, Inc.</p>
          <p class="text-center text-xs">•</p>
          <a
            href=""
            class="hover:underline"
            >Terms</a
          >
          <p class="text-center text-xs">•</p>
          <a
            href=""
            class="hover:underline"
            >Sitemap</a
          >
          <p class="text-center text-xs">•</p>
          <a
            href=""
            class="hover:underline"
            >Privacy</a
          >
          <p class="text-center text-xs">•</p>
          <a
            href=""
            class="hover:underline"
            >Your Privacy Choices</a
          >
          <p class="text-center text-xs">•</p>
          <a
            href=""
            class="hover:underline"
            >Destinations
          </a>
        </div>
        <!-- right footer-->
        <div
          class="flex flex-row flex-wrap items-center justify-end gap-2 text-xs font-bold lg:text-sm"
        >
          <GlobeAltIcon class="h-6 w-6" />
          <a
            href=""
            class="hover:underline"
            >English (US)
          </a>
          <p>Rp</p>
          <a
            href=""
            class="hover:underline"
            >IDR
          </a>
          <a
            href=""
            class="hover:underline"
            >Support & resources
          </a>
          <ChevronUpIcon class="h-6 w-6" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  GlobeAltIcon,
  UserIcon,
  HeartIcon,
  ChevronUpIcon,
  MagnifyingGlassIcon,
} from '@heroicons/vue/24/outline';
</script>
