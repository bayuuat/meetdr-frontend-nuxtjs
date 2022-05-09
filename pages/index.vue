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
        <QueueCard
          :isAuthenticated="isAuthenticated"
          :isOpen="isOpen"
          :totalPasien="totalPasien"
        />
        <div
          class="col-8 d-flex justify-content-center"
          v-if="!isAuthenticated"
        >
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
                  data-bs-target="#guestRegister"
                >
                  Register as Guest
                </button>
              </div>
              <div class="col-6 d-flex justify-content-end">
                <button
                  type="button"
                  class="btn btn-primary"
                  data-bs-toggle="modal"
                  data-bs-target="#userRegister"
                >
                  Register as User
                </button>
              </div>

              <RegisterModal />
              <GuestRegisterModal />
            </div>
          </div>
        </div>
        <div class="col-4" v-else>
          <div
            class="custom-card order-card shadow-sm h-100 d-flex flex-column justify-content-center"
          >
            <h2 class="text-center">Hallo, {{ loggedInUser.name }}</h2>
            <div class="" v-if="isOpen && !alreadyRegis">
              <h2 class="my-5 text-center">You are not on the queue</h2>
              <div class="d-flex justify-content-center">
                <button
                  type="button"
                  class="btn btn-primary"
                  data-bs-toggle="modal"
                  data-bs-target="#loginUserRegister"
                >
                  Register
                </button>
              </div>
            </div>
            <div class="" v-if="isOpen && alreadyRegis">
              <h1 class="my-5 text-center">1</h1>
              <h4 class="text-center">Order Number</h4>
            </div>
            <LoggedinRegisterModal />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import RegisterModal from "@/components/home/UserRegister.vue";
import LoggedinRegisterModal from "@/components/home/LoginUserRegister.vue";
import GuestRegisterModal from "@/components/home/GuestRegister.vue";
import QueueCard from "@/components/home/QueueCard.vue";

import { mapGetters } from "vuex";

export default {
  components: {
    RegisterModal,
    GuestRegisterModal,
    LoggedinRegisterModal,
    QueueCard,
  },

  data() {
    return {
      openHour: 17,
      closedHour: 24,
      isOpen: false,
      alreadyRegis: false,
      totalPasien: 0,
      pendaftar: [],
      timestamp: "",
    };
  },

  methods: {
    getNow: function () {
      const today = new Date();
      const time = today.getHours();
      this.timestamp = time;
    },
  },

  async fetch() {
    await this.$axios
      .get("pendaftar")
      .then((res) => [
        (this.totalPasien = res.data.data.total),
        (this.pendaftar = res.data.data.data),
      ]);
  },

  mounted() {
    this.getNow();
    if (this.timestamp > this.openHour && this.timestamp < this.closedHour) {
      this.isOpen = true;
    }
    for (let index = 0; index < this.pendaftar.length; index++) {
      const user_id = this.pendaftar[index].user_id;
      if (this.loggedInUser.id == user_id) {
        this.alreadyRegis = true;
      }
    }
  },

  computed: {
    ...mapGetters(["isAuthenticated", "loggedInUser"]),
  },
};
</script>
