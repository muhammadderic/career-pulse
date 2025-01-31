<script setup>
defineProps({
  bg: {
    type: String,
    default: "bg-gray-100",
  },
})
</script>

<template>
  <div :class="`${bg} p-6 rounded-lg border border-black-500`">
    <slot></slot>
  </div>
</template>