<template>
  <div>
    <button class="relative z-50 group focus-brand" @click="$emit('toggle')">
      <div
        class="relative flex items-center justify-center w-[35px] h-[27px] transform transition-all bg-transparent duration-200"
      >
        <span
          class="absolute top-0 left-0 w-full h-[0.2rem] transition-all ease-in-out transform rounded-full bg-light-menu-selection dark:bg-dark-menu-selection duration-250"
          :class="{ 'opacity-0': isMenuOpen }"
        ></span>
        <span
          class="absolute left-0 w-full h-[0.2rem] transition-all ease-in-out transform -translate-y-1/2 rounded-full bg-light-menu-selection dark:bg-dark-menu-selection top-1/2 duration-250"
          :class="{ 'rotate-45': isMenuOpen }"
        ></span>
        <span
          class="absolute left-0 w-full h-[0.2rem] transition-all ease-in-out transform -translate-y-1/2 rounded-full bg-light-menu-selection dark:bg-dark-menu-selection top-1/2 duration-250"
          :class="{ '-rotate-45': isMenuOpen }"
        ></span>
        <span
          class="absolute bottom-0 left-0 w-full h-[0.2rem] transition-all ease-in-out transform rounded-full bg-light-menu-selection dark:bg-dark-menu-selection duration-250"
          :class="{ 'opacity-0': isMenuOpen }"
        ></span>
      </div>
    </button>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  isMenuOpen: {
    type: Boolean,
    default: false,
  },
});

const emits = defineEmits(["toggle"]);
</script>
