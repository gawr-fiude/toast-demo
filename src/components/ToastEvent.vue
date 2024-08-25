<template>
  <li ref="toast" class="toast">
    <span>
      {{ msg }}
    </span>

    <button @click="$emit('close')">x</button>
  </li>
</template>

<script setup>
import { ref, onMounted } from "vue";

const props = defineProps({
  msg: String,
  timeout: Number,
});
const emit = defineEmits(["close"]);

const toast = ref();
onMounted(() => {
  if (props.timeout) {
    setTimeout(() => {
      toast.value.classList.add("toast--disappear");

      setTimeout(() => {
        emit("close");
      }, 500);
    }, props.timeout);
  }
});
</script>

<style scoped>
.toast {
  padding: 2rem;
  border: 1px solid rgba(255, 255, 255, 0.87);
  border-radius: 1rem;

  display: flex;
  gap: 1rem;
  place-items: center;

  animation: appear 0.3s forwards;
}

.toast--disappear {
  animation: disappear 0.3s forwards;
}

@keyframes appear {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
  }
}

@keyframes disappear {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
    transform: translateX(100%);
  }
}
</style>
