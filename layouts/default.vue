<template>
  <div>
    <Navbar class="sticky top-0 z-[100]" />
    <NavbarCategories class="sticky top-0 z-[99]" />
    <slot />

    <Footer class="sticky bottom-0 z-[100]" />
  </div>
</template>
