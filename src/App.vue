<script setup>
import { ref } from "vue";

import ToastEvent from "./components/ToastEvent.vue";

const toastEvents = ref([]);

function addToastEvent() {
  toastEvents.value.push({
    id: new Date(),
    msg: "Which is the Toast? 🥂🍞",
    timeout: 2000,
  });
}

function removeToastEvent(id) {
  toastEvents.value = toastEvents.value.filter((element) => element.id !== id);
}
</script>

<template>
  <button type="button" @click="addToastEvent">Toast</button>

  <ul id="toasts">
    <template v-for="event in toastEvents" :key="event.id">
      <ToastEvent
        @close="removeToastEvent(event.id)"
        :id="event.id"
        :msg="event.msg"
        :timeout="2000"
      />
    </template>
  </ul>
</template>

<style scoped>
#toasts {
  position: fixed;
  list-style-type: none;

  top: 0;
  right: 2rem;

  display: grid;
  gap: 1rem;
}
</style>
