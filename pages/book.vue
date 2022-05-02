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
        <div class="col mt-4">
          <div class="symptomp-card custom-card shadow-sm">
            <h3>Patient Symptoms</h3>
            <h4>
              My throat is pain and i feel soreness in there. I feel fever and
              fatigue all over my body.
            </h4>
            <h5>Since : 2 weeks ago</h5>
          </div>
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
