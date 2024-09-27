<template>
  <navbar />
  <main>
    <div class="max-w-[1200px] min-h-screen mx-auto mb-10">
      <router-view />
    </div>
  </main>
  <Footer />
</template>

<script setup>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
</script>
