<script setup>
import { onMounted } from "vue";
import { initFlowbite } from "flowbite";

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});
</script>
<template>
  <div class=" fixed top-0 left-0 z-40 w-64 h-screen transition-transform -translate-x-full sm:translate-x-0">
    <ul  class="flex items-center"
        v-for="item in items"
        :key="item.id">
      <RouterLink :to="item.name"
       
        @click="addTab(item)"
      >
        {{ item.name }}
      </RouterLink>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, name: "Página_1" },
        { id: 2, name: "Página_2" },
        { id: 3, name: "Página_3" },
      ],
    };
  },
  methods: {
    addTab(item) {
      this.$emit("addTab", item);
    },
  },
};
</script>
