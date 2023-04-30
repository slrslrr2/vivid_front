<template>
  <div
    class="w-full md:w-[365px] lg:w-[460px] flex flex-col p-3 sm:px-8 md:p-5 lg:p-[47px] bg-white dark:bg-[#17294E]"
  >
    <!--===== Aside header =====-->
    <Head />

    <!--===== Current Location =====-->
    <CurrentLocation />
  </div>
</template>

<script>
import Head from "./wrapper/_head.vue";
import CurrentLocation from "./wrapper/_currentLocation.vue";

export default {
  name: "aside-wrapper",
  components: {
    Head,
    CurrentLocation,
  },
};
</script>

<style></style>
