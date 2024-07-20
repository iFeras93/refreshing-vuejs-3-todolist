<template>
  <label
    class="group relative flex flex-row-reverse items-center justify-between gap-3"
  >
    <input
      type="checkbox"
      class="peer sr-only"
      id="switch1"
      name="switch1"
      checked
    />
    <span
      class="relative h-6 w-10 flex-none rounded-full bg-gray-300 transition-all duration-150 ease-out before:absolute before:left-1 before:top-1 before:size-4 before:rounded-full before:bg-white before:transition-transform before:duration-150 before:ease-out before:content-[''] peer-checked:bg-indigo-500 peer-checked:before:translate-x-full peer-focus:ring peer-focus:ring-indigo-500/50 peer-focus:ring-offset-2 peer-focus:ring-offset-white peer-disabled:cursor-not-allowed peer-disabled:opacity-75 dark:bg-gray-700 dark:peer-checked:bg-indigo-500 dark:peer-focus:ring-offset-gray-900"
    ></span>
    <span class="font-medium">
      <span>Account Notifications</span>
      <span class="block text-sm text-gray-500 dark:text-gray-400"
        >We will notify you about important changes</span
      >
    </span>
  </label>
</template>

<script></script>

<style></style>
