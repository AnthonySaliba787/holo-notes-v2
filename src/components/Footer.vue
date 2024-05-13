<template>
  <div
    class="w-full h-20 flex flex-col justify-center items-center text-center my-8"
  >
    <button
      @click="showModal = true"
      class="bg-black text-xl lg:text-2xl rounded-md shadow-md text-white font-medium px-12 py-4 hover:shadow-lg hover:bg-neutral-800 active:scale-95 duration-300"
    >
      Create
    </button>
  </div>
</template>

<script setup>
import { inject } from "vue";

const showModal = inject("showModal");
</script>
