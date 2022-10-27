<script setup>
defineProps({
  label: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="mb-[14px]">
    <label class="text-[13px] font-bold block mb-[4px]">{{ label }}</label>
    <slot></slot>
  </div>
</template>
