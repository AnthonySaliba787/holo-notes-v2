<template>
  <div
    class="w-full flex-1 flex flex-col flex-wrap md:flex-row justify-center items-center text-center my-8 py-8 overflow-x-hidden overflow-y-auto gap-4"
  >
    <div
      v-for="note in notes"
      :key="note.id"
      @click="note.expandNote = true"
      class="w-80 h-80 my-4 text-xl bg-white lg:text-2xl text-neutral-900 font-medium cursor-pointer flex justify-center items-center shadow-xl rounded-md hover:scale-105 hover:bg-neutral-900 hover:text-white duration-300"
    >
      <h1>
        {{ note.title }}
      </h1>
    </div>
  </div>
</template>

<script setup>
import { inject } from "vue";

const notes = inject("notes");
</script>
