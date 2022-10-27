<script setup>
defineProps({
  type: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <button :type="type" class="block bg-black rounded-md w-full h-[40px]">
    <slot></slot>
  </button>
</template>
