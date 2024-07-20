<template>
  <!-- Form Switches: In List Group -->
  <ul
    class="divide-y divide-gray-200 rounded-lg border border-gray-200 bg-white dark:divide-gray-700 dark:border-gray-700 dark:bg-gray-900 dark:text-gray-100"
  >
    <li class="p-4">
      <TodoItem />
    </li>
  </ul>
  <!-- END Form Switches: In List Group -->
</template>

<script>
import TodoItem from "./Item.vue";
export default {
  components: {
    TodoItem,
  },
};
</script>

<style></style>
