<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div>
    <div class="font-bold text-[15px] mb-[15px]">{{ title }}</div>
    <slot></slot>
  </div>
</template>
