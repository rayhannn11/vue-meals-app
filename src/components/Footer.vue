<template>
  <div class="bg-white text-orange-500 font-bold p-3">
    <div class="flex flex-col md:flex-row justify-between items-center">
      <!-- Bagian icon -->
      <div class="flex p-4 items-center gap-3">
        <a href="https://github.com/rayhannn11" target="_blank">
          <img src="../assets/github.png" alt="github-social" class="w-14" />
        </a>
        <a
          href="https://www.linkedin.com/in/rayhan-naufal-arrafi-b02175229/"
          target="_blank"
        >
          <img
            src="../assets/linkedin.png"
            alt="linkin-social"
            class="w-11 rounded-sm"
          />
        </a>
      </div>

      <!-- Bagian copyright -->
      <div class="mr-4">
        <p class="text-xl">&copy; {{ currentYear }} - Rayhan Naufal Arrafi</p>
      </div>
    </div>
  </div>
</template>

<script setup>
// import VIcon from "vue-icon";

const currentYear = new Date().getFullYear();
</script>
