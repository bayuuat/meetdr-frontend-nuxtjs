<template>
  <div class="home-page mx-5">
    <section class="hero py-5">
      <div class="d-flex justify-content-between">
        <div class="text col-6 align-self-center">
          <h1 class="title">Welcome to Massachusetts General Hospital</h1>
          <h3>
            Massachusetts General Hospital (Mass General or MGH) is the original
            and largest teaching hospital of Harvard Medical School located in
            the West End neighborhood of Boston, Massachusetts. It is the third
            oldest general hospital in the United States.It is currently ranked
            as the #5 best hospital in the United States by U.S. News & World
            Report.
          </h3>
        </div>
        <div class="col-auto">
          <img src="~/assets/hero.png" alt="" style="width: 30vw" />
        </div>
      </div>
    </section>
    <div class="queue py-3">
      <div class="row">
        <div class="col-4">
          <div class="custom-card queue-card shadow-sm">
            <div class="header d-flex justify-content-between">
              <h2>Queue</h2>
              <div class="align-self-center">
                <i class="fas fa-ellipsis-v"></i>
              </div>
            </div>
            <h1 class="my-5 text-center">1/20</h1>
            <h4>Registration is open until 19:00</h4>
          </div>
        </div>
        <div class="col-8 d-flex justify-content-center">
          <div class="col-8 cta d-flex flex-column justify-content-between">
            <h1 class="text-center">
              Want to get in the queue and haven't registered yet?
            </h1>
            <div class="row">
              <div class="col-6">
                <button
                  type="button"
                  class="btn btn-outline-secondary"
                  data-bs-toggle="modal"
                  data-bs-target="#staticBackdrop"
                >
                  Register as Guest
                </button>
              </div>
              <div class="col-6 d-flex justify-content-end">
                <button
                  type="button"
                  class="btn btn-primary"
                  data-bs-toggle="modal"
                  data-bs-target="#staticBackdrop"
                >
                  Register as User
                </button>
              </div>

              <RegisterModal />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import RegisterModal from "@/components/home/RegisterModal.vue";
export default {
  components: { RegisterModal },
};
</script>
