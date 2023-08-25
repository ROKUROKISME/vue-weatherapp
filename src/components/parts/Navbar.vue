<template>
  <div>
    <header class="fixed w-full bg-slate-100 bg-opacity-50 backdrop-blur-sm mb-10">
      <Transition name="slide-fade" :duration="{ enter: 500, leave: 800 }">
        <div v-if="isNavbar" class="fixed flex-row w-1/2 h-screen flex z-50 overflow-y-scroll scrollbar-hide bg-slate-100 bg-opacity-80 backdrop-blur-sm mb-10">
          <div class="absolute top-0 right-0">
            <button @click="toggleNavbar" class="m-3 rounded-full flex h-5 w-5 items-center justify-center z-auto">
              <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512">
                <!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                <path
                  d="M342.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L192 210.7 86.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L146.7 256 41.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 301.3 297.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L237.3 256 342.6 150.6z"
                />
              </svg>
            </button>
          </div>
          <ul class="mt-8 w-full text-bold">
            <li class="m-2 p-2 flex rounded-lg">
              <MyButton :class="{ active: this.$route.path === '/' }" link="/" title="Home" />
            </li>
            <li class="m-2 p-2 flex rounded-lg">
              <MyButton :class="{ active: this.$route.path === '/product' }" link="/product" title="Product" />
            </li>
            <li class="m-2 p-2 flex rounded-lg">
              <MyButton :class="{ active: this.$route.path === '/sosial' }" link="/sosial" title="Sosial" />
            </li>
            <li class="m-2 p-2 flex rounded-lg">
              <MyButton :class="{ active: this.$route.path === '/pricing' }" link="/pricing" title="Pricing" />
            </li>
            <li class="m-2 p-2 flex rounded-lg">
              <MyButton :class="{ active: this.$route.path === '/login' }" link="/login" title="Login" />
            </li>

            <li class="m-2 p-2 flex rounded-lg">
              <a
                href="#"
                title=""
                class="inline-flex items-center justify-center px-5 py-2.5 text-base font-semibold text-black border-2 border-black hover:bg-black hover:text-white transition-all duration-200 focus:bg-black focus:text-white"
                role="button"
              >
                Try for free
              </a>
            </li>
          </ul>
        </div>
      </Transition>
      <div class="px-4 mx-auto sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-16 lg:h-20">
          <div class="flex-shrink-0">
            <a href="/" title="" class="flex">
              <img class="w-auto h-8" src="https://cdn.rareblocks.xyz/collection/celebration/images/hero/2/logo.svg" alt="" />
            </a>
          </div>

          <button type="button" @click="toggleNavbar" class="inline-flex p-1 text-black transition-all duration-200 border border-black lg:hidden focus:bg-gray-100 hover:bg-gray-100" :class="{ hidden: isNavbar }">
            <!-- Menu open: "hidden", Menu closed: "block" -->
            <svg class="block w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <!-- Menu open: "block", Menu closed: "hidden" -->
            <svg class="hidden w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>

          <div class="hidden ml-auto lg:flex lg:items-center lg:justify-center lg:space-x-10">
            <RouterLink :to="{ name: 'home' }" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80"> Home </RouterLink>

            <RouterLink :to="{ name: 'product' }" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80"> Product </RouterLink>

            <RouterLink :to="{ name: 'sosial' }" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80"> Sosial </RouterLink>

            <RouterLink :to="{ name: 'pricing' }" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80"> Pricing </RouterLink>

            <div class="w-px h-5 bg-black/20"></div>

            <RouterLink :to="{ name: 'login' }" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80"> Log in </RouterLink>

            <button
              href="#"
              title=""
              class="inline-flex items-center justify-center px-5 py-2.5 text-base font-semibold text-black border-2 border-black hover:bg-black hover:text-white transition-all duration-200 focus:bg-black focus:text-white"
              role="button"
            >
              Try for free
            </button>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>

<script setup>
import { RouterLink } from "vue-router";
import { ref } from "vue";
import MyButton from "@/components/button/ButtonA.vue";

const isNavbar = ref(false);
const toggleNavbar = () => {
  isNavbar.value = !isNavbar.value;
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(-100px);
  opacity: 0;
}

/* hide scrollbar */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}

/* For IE, Edge and Firefox */
.scrollbar-hide {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

.active {
  opacity: 0.8;
  color: blueviolet;
  padding-left: 10px;
  border-left: 5px solid blueviolet;
}
</style>
