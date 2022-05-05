<template>
  <div
    class="notification p-3 mb-3 bg-danger bg-gradient text-white text-center"
  >
    {{ message }}
  </div>
</template>

<script>
export default {
  name: "Notification",
  props: ["message"],
};
</script>
