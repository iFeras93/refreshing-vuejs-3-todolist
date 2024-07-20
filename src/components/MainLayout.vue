<script setup>
import Header from "./partials/Header.vue";
import Footer from "./partials/Footer.vue";
</script>

<template>
  <!-- Page Container -->
  <div
    id="page-container"
    class="mx-auto flex min-h-dvh w-full min-w-[320px] flex-col bg-gray-100 dark:bg-gray-900 dark:text-gray-100"
  >
    <!-- Page Header -->
    <Header />
    <!-- END Page Header -->

    <!-- Page Content -->
    <main id="page-content" class="flex max-w-full flex-auto flex-col">
      <!-- Page Section -->
      <div class="container mx-auto p-4 lg:p-8 xl:max-w-7xl">
        <!--

        ADD YOUR MAIN CONTENT BELOW

        -->

        <slot></slot>

        <!--
        
        ADD YOUR MAIN CONTENT ABOVE
              
        -->
      </div>
      <!-- END Page Section -->
    </main>
    <!-- END Page Content -->

    <!-- Page Footer -->
    <Footer />
    <!-- END Page Footer -->
  </div>
  <!-- END Page Container -->
</template>
