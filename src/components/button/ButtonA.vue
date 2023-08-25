<template>
  <a :href="'' + link" class="text-base font-semibold text-black transition-all duration-200 hover:text-opacity-80 hover:text-blue-700 hover:pl-3 hover:border-l-4 hover:border-blue-700"> {{ title }} </a>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  link: String,
  title: String,
  isActive: Number,
});
</script>
