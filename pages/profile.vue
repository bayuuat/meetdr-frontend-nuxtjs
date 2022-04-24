<template>
  <div class="profile">
    <div class="row">
      <div class="col-9">
        <div class="col">
          <div class="profile-card shadow-sm">
            <div class="row">
              <div class="main col-3">
                <div class="row top">
                  <div class="col-auto">
                    <img src="~/assets/icon_profile.png" alt="" />
                  </div>
                  <div class="col name align-self-center">
                    <h3>Bayu Aditya T</h3>
                    <h5>20 years old</h5>
                  </div>
                </div>
                <div class="row bott">
                  <div class="col">
                    <h5>Height</h5>
                    <h4>175</h4>
                  </div>
                  <div class="col">
                    <h5>Weight</h5>
                    <h4>80</h4>
                  </div>
                  <div class="col">
                    <h5>Blood type</h5>
                    <h4>O+</h4>
                  </div>
                </div>
              </div>
              <div
                class="side col-9 d-flex flex-column justify-content-between"
              >
                <div class="row">
                  <div class="col">
                    <h5>Phone number</h5>
                    <h4>+62 812 3015 2397</h4>
                  </div>
                  <div class="col">
                    <h5>Email</h5>
                    <h4>joedhn@email.com</h4>
                  </div>
                  <div class="col">
                    <h5>ID</h5>
                    <h4>35991256080001</h4>
                  </div>
                </div>
                <div class="row">
                  <div class="col">
                    <h5>Patient ID</h5>
                    <h4>1267678</h4>
                  </div>
                  <div class="col-8">
                    <h5>Medical Conditions</h5>
                    <h4>Alergies, Atsma, Cold, Coronary Heart</h4>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col mt-4">
          <StatusCard />
        </div>
        <div class="row mt-4">
          <LastCard />
          <MedicineCard />
        </div>
      </div>
      <div class="col-3">
        <div class="side-card">
          <div class="custom-card shadow-sm h-100"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import StatusCard from "@/components/profile/StatusCard.vue";
import LastCard from "@/components/profile/LastCard.vue";
import MedicineCard from "@/components/profile/MedicineCard.vue";
export default {
  components: { StatusCard, LastCard, MedicineCard },
};
</script>

<style></style>
