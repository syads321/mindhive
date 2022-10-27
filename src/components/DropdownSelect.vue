<script>
import { ref } from "vue";
import InputText from "./InputText.vue";
export default {
  components: {
    InputText,
  },
  setup() {
    let show = ref(false);
    let selectedList = ref(null);
    const isOpen = () => (show.value = !show.value);
    const select = (val) => {
      selectedList.value = val;
      show.value = false;
    };
    return { show, isOpen, selectedList, select };
  },
};
</script>

<template>
  <div>
    <div class="relative cursor-pointer">
      <InputText
        type="text"
        rounded="rounded-t-md"
        border="border-t border-r border-l"
        @click="isOpen"
        placeholder="America"
        :value="selectedList"
      >
        <svg
          :class="`w-5 h-5 text-black dark:text-white ${
            show ? 'rotate-180' : ''
          }`"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
            clip-rule="evenodd"
          />
        </svg>
      </InputText>
      <!-- Dropdown menu -->
      <div
        v-show="show"
        class="absolute right-0 py-2 mt-2 bg-white rounded-md shadow-xl w-44"
        style="z-index: 100"
      >
        <div
          class="block px-4 py-2 text-sm hover:bg-black hover:text-white"
          @click="() => select('America')"
        >
          America
        </div>
        <div
          to="/"
          class="block px-4 py-2 text-sm hover:bg-black hover:text-white"
          @click="() => select('Singapore')"
        >
          Singapore
        </div>
        <div
          class="block px-4 py-2 text-sm hover:bg-black hover:text-white"
          @click="() => select('Indonesia')"
        >
          Indonesia
        </div>
      </div>
    </div>
  </div>
</template>
