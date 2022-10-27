<script setup>
defineProps({
  type: {
    type: String,
    required: true,
  },
  rounded: {
    type: String,
  },
  border: {
    type: String,
  },
  placeholder: {
    type: String,
  },
  value: {
    type: String,
  },
});
</script>

<template>
  <div class="relative">
    <input
      :type="type"
      :class="`${border} border-slate-400 border-gray w-full h-[36px] ${rounded} px-3`"
      :placeholder="placeholder"
      :value="value"
    />
    <div class="absolute top-[12px] right-4">
      <slot></slot>
    </div>
  </div>
</template>
