<script>
import List from "./todos/List.vue";
import ModalDialog from "./todos/ModalDialog.vue";

export default {
  components: {
    List,
    ModalDialog,
  },
  props: {
    cardTitle: {
      type: String,
      default: "Todo List",
    },
  },
  data() {
    return {
      openModal: false,
    };
  },
  methods: {
    handleModalDialog() {
      this.openModal = !this.openModal;
    },
  },
};
</script>

<template>
  <!-- Card Headings: Title with Subtitle and Action -->
  <div
    class="flex flex-col overflow-hidden rounded-lg bg-white shadow-sm dark:bg-gray-800 dark:text-gray-100"
  >
    <!-- Card Header -->
    <div
      class="flex flex-col gap-3 bg-gray-50 px-5 py-4 text-center sm:flex-row sm:items-center sm:justify-between sm:gap-0 sm:text-left dark:bg-gray-700/50"
    >
      <div>
        <h3 class="mb-1 font-semibold">{{ cardTitle }}</h3>
        <h4 class="text-sm font-medium text-gray-500 dark:text-gray-400">
          You have
          <a
            href="#"
            class="text-indigo-600 hover:text-indigo-400 dark:text-indigo-400 dark:hover:text-indigo-300"
            >3 Completed tasks</a
          >
          and
          <a
            href="#"
            class="text-indigo-600 hover:text-indigo-400 dark:text-indigo-400 dark:hover:text-indigo-300"
            >1 Uncompleted</a
          >
        </h4>
      </div>
      <div>
        <a
          @click.prevent="handleModalDialog()"
          href="#"
          class="inline-flex items-center justify-center gap-2 rounded-lg border border-indigo-700 bg-indigo-700 px-3 py-2 text-sm font-semibold leading-5 text-white hover:border-indigo-600 hover:bg-indigo-600 hover:text-white focus:ring focus:ring-indigo-400/50 active:border-indigo-700 active:bg-indigo-700 dark:focus:ring-indigo-400/90"
        >
          <svg
            class="hi-mini hi-plus inline-block size-4 opacity-50"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              d="M10.75 4.75a.75.75 0 00-1.5 0v4.5h-4.5a.75.75 0 000 1.5h4.5v4.5a.75.75 0 001.5 0v-4.5h4.5a.75.75 0 000-1.5h-4.5v-4.5z"
            />
          </svg>
          <span>New Task</span>
        </a>
      </div>
    </div>
    <!-- END Card Header -->

    <!-- Card Body -->
    <div class="grow p-5">
      <List />
    </div>
    <!-- Card Body -->
  </div>
  <!-- END Card Headings: Title with Subtitle and Action -->
  <ModalDialog :isOpen="openModal" @modal:close="handleModalDialog()" />
</template>
