<template>
  <div class="profile">
    <div class="row">
      <div class="col-auto">
        <div class="profile-list">
          <div class="col">
            <div class="custom-card diagnos-card shadow-sm">
              <h2>Last Checkup</h2>
              <div class="row d-flex align-items-center">
                <div class="col-auto">
                  <i class="fas fa-disease icon-top"></i>
                </div>
                <div class="col">
                  <h3>Heart Disease</h3>
                  <h4>Dilated Cardiomyopathy</h4>
                </div>
              </div>
              <div class="bot">
                <div class="d-flex align-items-center">
                  <h5 class="me-auto">Illness History</h5>
                  <i class="fas fa-chevron-right ms-auto"></i>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-7">
        <div class="col">
          <StatusCard />
        </div>
        <div class="row mt-4">
          <LastCard />
          <div class="col">
            <div class="custom-card diagnos-card shadow-sm">
              <h2>Last Checkup</h2>
              <div class="row d-flex align-items-center">
                <div class="col-auto">
                  <i class="fas fa-disease icon-top"></i>
                </div>
                <div class="col">
                  <h3>Heart Disease</h3>
                  <h4>Dilated Cardiomyopathy</h4>
                </div>
              </div>
              <div class="bot">
                <div class="d-flex align-items-center">
                  <h5 class="me-auto">Illness History</h5>
                  <i class="fas fa-chevron-right ms-auto"></i>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import StatusCard from "@/components/profile/StatusCard.vue";
import LastCard from "@/components/profile/LastCard.vue";
export default {
  components: { StatusCard, LastCard },
};
</script>

<style></style>
