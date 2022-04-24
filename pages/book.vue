<template>
  <div class="bookmark">
    <div class="row">
      <div class="profile-list col-auto">
        <div class="profile-list-card shadow-sm">
          <div class="header d-flex justify-content-between">
            <h2>Patient List</h2>
            <div class="align-self-center">
              <i class="fas fa-search me-4"></i>
              <i class="fas fa-ellipsis-v"></i>
            </div>
          </div>
          <PatientList />
          <PatientList />
          <PatientList />
          <PatientList />
        </div>
      </div>
      <div class="col-7">
        <div class="col">
          <StatusCard />
        </div>
        <div class="row mt-4">
          <LastCard />
          <MedicineCard />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PatientList from "@/components/book/PatientList.vue";
import StatusCard from "@/components/profile/StatusCard.vue";
import LastCard from "@/components/profile/LastCard.vue";
import MedicineCard from "@/components/profile/MedicineCard.vue";
export default {
  components: { PatientList, StatusCard, LastCard, MedicineCard },
};
</script>

<style></style>
