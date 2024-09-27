<template>
  <div class="p-8 pb-0">
    <h1 class="text-4xl font-bold mb-4 text-orange-500">Meals by Letter</h1>
  </div>
  <div class="flex flex-wrap justify-center gap-3 px-8 mb-6">
    <router-link
      :to="{ name: 'byLetter', params: { letter } }"
      v-for="letter of letters"
      :key="letter"
      class="w-2 h-2 flex items-center justify-center hover:text-orange-500 hover:scale-150 transition-all"
    >
      <h4 :class="{ 'text-orange-500': route.params.letter === letter }">
        {{ letter }}
      </h4>
    </router-link>
  </div>

  <Meals :meals="meals" />
</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, watch } from "vue";
import { useRoute, useRouter } from "vue-router";
import store from "../store";
import Meals from "../components/Meals.vue";

const route = useRoute();
const router = useRouter();
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
const meals = computed(() => store.state.mealsByLetter);

console.log(route.params.letter);

watch(route, () => {
  store.dispatch(
    "searchMealsByLetter",
    route.params.letter ? route.params.letter : "A"
  );
});

onMounted(() => {
  if (!route.params.letter) {
    router.push({ name: route.name, params: { letter: "A" } });
  } else {
    // Jika sudah ada parameter `letter`, jalankan aksi store
    store.dispatch("searchMealsByLetter", route.params.letter);
  }
});
</script>
