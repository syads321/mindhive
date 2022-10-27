<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <label class="flex">
    <input type="checkbox" class="w-[15px] h-[15px] mt-[3px]" />
    <div class="pl-3 font-bold text-[13px]">{{ title }}</div>
  </label>
</template>
