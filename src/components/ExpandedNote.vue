<template>
  <div v-for="note in notes" :key="note.id">
    <div
      v-if="note.expandNote"
      class="absolute w-screen min-h-dvh z-20 bg-neutral-100/80 backdrop-blur-lg flex flex-col justify-center items-center"
    >
      <div
        class="w-full h-screen flex justify-between items-center flex-col gap-4 px-8"
      >
        <div class="w-full flex justify-center items-center flex-col">
          <h2 class="text-2xl font-bold py-12 text-center">
            {{ note.title }}
          </h2>
        </div>
        <div class="w-full flex justify-center items-center flex-col">
          <p
            class="w-full max-h-96 text-lg text-justify break-words overflow-x-hidden overflow-y-auto"
          >
            {{ note.desc }}
          </p>
        </div>
        <div
          class="w-full flex flex-row justify-center items-center py-4 gap-4"
        >
          <button
            class="bg-red-600 w-44 h-14 text-lg lg:text-xl my-2 rounded-md shadow-md text-white font-medium hover:shadow-lg hover:bg-red-400 active:scale-95 duration-300"
            @click="deleteNote(note.id)"
          >
            Delete
          </button>
          <button
            class="bg-black w-44 h-14 text-lg lg:text-xl my-2 rounded-md shadow-md text-white font-medium hover:shadow-lg hover:bg-neutral-800 active:scale-95 duration-300"
            @click="note.expandNote = false"
          >
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { inject } from "vue";

const notes = inject("notes");
const emit = defineEmits(["deleteNote"]);

function deleteNote(noteID) {
  emit("deleteNote", noteID);
}
</script>
