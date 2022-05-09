<template>
  <div
    class="modal"
    id="loginUserRegister"
    tabindex="-1"
    aria-labelledby="loginUserRegisterLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="loginUserRegisterLabel">
            {{ isLogin ? "Sign In" : "Registration" }}
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <form method="post" @submit.prevent="queue">
          <div class="modal-body">
            <Notification :message="error" v-if="error" />
            <div class="mb-3">
              <label for="inputEmail" class="col-form-label"
                >How you feel?</label
              >
              <textarea
                class="form-control"
                id="inputComplaint"
                rows="4"
                name="complaint"
                v-model="complaint"
              ></textarea>
            </div>
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <button type="submit" class="btn btn-primary">Submit</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Notification from "~/components/Notification";

export default {
  components: {
    Notification,
  },

  data() {
    return {
      isLogin: false,
      complaint: "",
      error: null,
    };
  },

  methods: {
    async queue() {
      try {
        await this.$axios.post("queue", {
          user_id: this.$auth.user.id,
          keluhan: this.complaint,
        });
        this.$router.go();
      } catch (e) {
        console.log(this.$auth.user.id, this.complaint);
        this.error = e.response.data.data.message;
      }
    },
    async login() {
      try {
        await this.$auth.loginWith("local", {
          data: {
            email: this.email,
            password: this.password,
          },
        });
        this.$router.go();
      } catch (e) {
        this.error = e.response.data.meta.message;
        console.log(this.error);
      }
    },
  },
};
</script>

<style></style>
