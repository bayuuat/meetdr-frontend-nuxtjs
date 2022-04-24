<template>
  <div class="col">
    <div class="custom-card meds-card shadow-sm">
      <div class="row">
        <div class="col">
          <h2>Medicine</h2>
          <MedList />
          <MedList />
          <MedList />
        </div>
        <div class="col-1">
          <div class="vertical-line"></div>
        </div>
        <div class="col">
          <h2>Document</h2>
          <DocList />
          <DocList />
          <DocList />
          <DocList />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MedList from "@/components/profile/MedList.vue";
import DocList from "@/components/profile/DocList.vue";
export default {
  components: {
    MedList,
    DocList,
  },
};
</script>

<style></style>
