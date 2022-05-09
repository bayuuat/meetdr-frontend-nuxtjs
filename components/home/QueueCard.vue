<template>
  <div class="col-4">
    <div
      class="custom-card queue-card shadow-sm h-100"
      v-if="isOpen && isAuthenticated"
    >
      <div class="header d-flex justify-content-between">
        <h2>Queue</h2>
        <div class="align-self-center">
          <i class="fas fa-ellipsis-v"></i>
        </div>
      </div>
      <h1 class="my-5 text-center">1/{{ totalPasien }}</h1>
      <h4>Registration is open until 19:00</h4>
    </div>
    <div
      class="custom-card queue-card shadow-sm h-100"
      v-if="isOpen && !isAuthenticated"
    >
      <h1 class="my-5 text-center">OPEN</h1>
      <h4 class="text-center">Registration is open until 19:00</h4>
    </div>
    <div class="custom-card queue-card shadow-sm h-100 closed" v-if="!isOpen">
      <h1 class="my-5 text-center">CLOSED</h1>
      <h4 class="text-center">Registration will open at 16:00</h4>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isAuthenticated: {
      type: Boolean,
      required: true,
      default: false,
    },
    isOpen: {
      type: Boolean,
      required: true,
      default: false,
    },
    totalPasien: {
      type: Number,
      required: true,
      default: 0,
    },
  },
};
</script>

<style></style>
