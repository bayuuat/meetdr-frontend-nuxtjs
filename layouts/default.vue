<template>
  <div id="app">
    <div class="container-fluid">
      <div class="row">
        <div class="col-auto px-0">
          <Sidebar />
        </div>
        <div class="col p-5">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/Sidebar.vue";
export default {
  components: { Sidebar },
};
</script>

<style></style>
