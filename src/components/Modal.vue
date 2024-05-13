<template>
  <div
    class="w-[20rem] sm:w-[30rem] bg-white rounded-md shadow-xl flex flex-col justify-center items-center my-8"
  >
    <h2 class="text-2xl lg:text-3xl font-bold px-4 py-4 my-4 text-center">
      Create Note
    </h2>
    <textarea
      v-model.trim="newTitle"
      name="title"
      id="title"
      placeholder="Title..."
      class="w-3/4 px-4 py-4 resize-none text-lg lg:text-xl my-4 rounded-md border-2 hover:border-black duration-300"
    ></textarea>
    <textarea
      v-model.trim="newDesc"
      name="note"
      id="note"
      placeholder="Description..."
      class="w-3/4 px-4 py-4 resize-none text-lg lg:text-xl my-4 rounded-md border-2 hover:border-black duration-300"
    ></textarea>
    <button
      class="bg-black w-44 h-14 text-lg lg:text-xl my-2 rounded-md shadow-md text-white font-medium hover:shadow-lg hover:bg-neutral-800 active:scale-95 duration-300"
      @click="triggerAddNote"
    >
      Create
    </button>
    <button
      class="bg-black w-44 h-14 text-lg lg:text-xl my-4 rounded-md shadow-md text-white font-medium hover:shadow-lg hover:bg-neutral-800 active:scale-95 duration-300"
      @click="showModal = false"
    >
      Close
    </button>
  </div>
</template>

<script setup>
import { inject, defineEmits } from "vue";

const showModal = inject("showModal");
const newTitle = inject("newTitle");
const newDesc = inject("newDesc");
const emit = defineEmits(["addNote"]);

function triggerAddNote() {
  emit("addNote");
}
</script>
