<script setup>
import { ref, watch } from "vue";

// Headless UI 1.x for Vue.js, for more info and examples you can check out https://github.com/tailwindlabs/headlessui
import {
  TransitionRoot,
  TransitionChild,
  Dialog,
  DialogPanel,
  DialogTitle,
} from "@headlessui/vue";

const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
});
const emits = defineEmits(["modal:close"]);
const isOpen = ref(props.isOpen);

const closeModal = () => {
  emits("modal:close");
  isOpen.value = false;
};

// Watch for changes in the props and update the internal state
watch(
  () => props.isOpen,
  (newVal) => {
    console.log(newVal);
    isOpen.value = newVal;
  },
);
</script>

<template>
  <!-- Modals: With Form -->
  <div>
    <!-- Modal Container -->
    <TransitionRoot appear :show="isOpen" as="template">
      <Dialog as="div" @close="closeModal" class="relative z-90">
        <!-- Modal Backdrop -->
        <TransitionChild
          as="template"
          enter="ease-out duration-200"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="ease-in duration-100"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-gray-900/75 backdrop-blur-sm" />
        </TransitionChild>
        <!-- END Modal Backdrop -->

        <!-- Modal Dialog -->
        <div class="fixed inset-0 overflow-y-auto p-4 lg:p-8">
          <TransitionChild
            as="template"
            enter="ease-out duration-200"
            enter-from="opacity-0 scale-125"
            enter-to="opacity-100 scale-100"
            leave="ease-in duration-100"
            leave-from="opacity-100 scale-100"
            leave-to="opacity-0 scale-125"
          >
            <DialogPanel
              class="mx-auto flex w-full max-w-md flex-col overflow-hidden rounded-lg bg-white shadow-sm dark:bg-gray-800 dark:text-gray-100"
            >
              <div
                class="flex items-center justify-between bg-gray-50 px-5 py-4 dark:bg-gray-700/50"
              >
                <h3 class="flex items-center gap-2 font-medium">
                  <svg
                    class="hi-mini hi-user-plus inline-block size-5 opacity-50"
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                    aria-hidden="true"
                  >
                    <path
                      d="M11 5a3 3 0 11-6 0 3 3 0 016 0zM2.615 16.428a1.224 1.224 0 01-.569-1.175 6.002 6.002 0 0111.908 0c.058.467-.172.92-.57 1.174A9.953 9.953 0 018 18a9.953 9.953 0 01-5.385-1.572zM16.25 5.75a.75.75 0 00-1.5 0v2h-2a.75.75 0 000 1.5h2v2a.75.75 0 001.5 0v-2h2a.75.75 0 000-1.5h-2v-2z"
                    />
                  </svg>
                  <span>Invite People</span>
                </h3>
                <div class="-my-4">
                  <button
                    @click="closeModal"
                    type="button"
                    class="inline-flex items-center justify-center gap-2 rounded-lg border border-transparent px-3 py-2 text-sm font-semibold leading-5 text-gray-800 hover:border-gray-300 hover:text-gray-900 hover:shadow-sm focus:ring focus:ring-gray-300/25 active:border-gray-200 active:shadow-none dark:border-transparent dark:text-gray-300 dark:hover:border-gray-600 dark:hover:text-gray-200 dark:focus:ring-gray-600/40 dark:active:border-gray-700"
                  >
                    <svg
                      class="hi-solid hi-x -mx-1 inline-block size-4"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                        clip-rule="evenodd"
                      ></path>
                    </svg>
                  </button>
                </div>
              </div>
              <div class="grow p-5">
                <p class="mb-3 text-sm">
                  Invite a friend or a colleague to your app and add them in
                  your current project.
                </p>
                <input
                  type="email"
                  id="email"
                  name="email"
                  placeholder="user@example.com"
                  class="block w-full rounded-lg border border-gray-200 px-3 py-2 text-sm leading-5 placeholder-gray-500 focus:border-indigo-500 focus:ring focus:ring-indigo-500/50 dark:border-gray-600 dark:bg-gray-800 dark:placeholder-gray-400 dark:focus:border-indigo-500"
                />
              </div>
              <div
                class="space-x-2 bg-gray-50 px-5 py-4 text-right dark:bg-gray-700/50"
              >
                <button
                  @click="closeModal"
                  type="button"
                  class="inline-flex items-center justify-center gap-2 rounded-lg border border-gray-200 bg-white px-3 py-2 text-sm font-semibold leading-5 text-gray-800 hover:border-gray-300 hover:text-gray-900 hover:shadow-sm focus:ring focus:ring-gray-300/25 active:border-gray-200 active:shadow-none dark:border-gray-700 dark:bg-gray-800 dark:text-gray-300 dark:hover:border-gray-600 dark:hover:text-gray-200 dark:focus:ring-gray-600/40 dark:active:border-gray-700"
                >
                  Cancel
                </button>
                <button
                  @click="closeModal"
                  type="button"
                  class="inline-flex items-center justify-center gap-2 rounded-lg border border-indigo-700 bg-indigo-700 px-3 py-2 text-sm font-semibold leading-5 text-white hover:border-indigo-600 hover:bg-indigo-600 hover:text-white focus:ring focus:ring-indigo-400/50 active:border-indigo-700 active:bg-indigo-700 dark:focus:ring-indigo-400/90"
                >
                  Send Invitation
                </button>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
        <!-- END Modal Dialog -->
      </Dialog>
    </TransitionRoot>
    <!-- END Modal Container -->
  </div>
  <!-- END Modals: With Form -->
</template>
