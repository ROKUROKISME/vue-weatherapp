<script setup>
import { RouterLink, RouterView } from "vue-router";
import Navbar from "@/components/parts/Navbar.vue";
import Footer from "./components/parts/Footer.vue";
</script>

<template>
  <Navbar />
  <RouterView />
  <Footer />
</template>
