<template>
  <div
    class="modal"
    id="userRegister"
    tabindex="-1"
    aria-labelledby="userRegisterLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="userRegisterLabel">
            {{ isLogin ? "Sign In" : "Registration" }}
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <form method="post" @submit.prevent="register" v-if="!isLogin">
          <div class="modal-body">
            <Notification :message="error" v-if="error" />
            <div class="mb-3 row">
              <label for="nameForm" class="col-sm-2 col-form-label">Name</label>
              <div class="col-sm-10">
                <input
                  type="text"
                  class="form-control"
                  id="nameForm"
                  name="name"
                  v-model="name"
                />
              </div>
            </div>
            <div class="mb-3 row">
              <label for="NIKForm" class="col-sm-2 col-form-label">NIK</label>
              <div class="col-sm-10">
                <input
                  type="text"
                  class="form-control"
                  id="NIKForm"
                  name="NIK"
                  v-model="nik"
                />
              </div>
            </div>
            <div class="mb-3 row">
              <label for="phoneForm" class="col-sm-2 col-form-label"
                >Phone</label
              >
              <div class="col-sm-10">
                <input
                  type="text"
                  class="form-control"
                  id="phoneForm"
                  name="phone"
                  v-model="phone"
                />
              </div>
            </div>
            <div class="mb-3 row">
              <label for="inputEmail" class="col-sm-2 col-form-label"
                >Email</label
              >
              <div class="col-sm-10">
                <input
                  type="text"
                  class="form-control"
                  id="inputEmail"
                  name="email"
                  v-model="email"
                />
              </div>
            </div>
            <div class="mb-3 row">
              <label for="inputPassword" class="col-sm-2 col-form-label"
                >Password</label
              >
              <div class="col-sm-10">
                <input
                  type="password"
                  class="form-control"
                  id="inputPassword"
                  name="password"
                  v-model="password"
                />
              </div>
            </div>
          </div>
          <div class="modal-footer justify-content-between">
            <button
              type="button"
              class="btn btn-success"
              @click="isLogin = !isLogin"
            >
              Login
            </button>
            <div class="">
              <button
                type="button"
                class="btn btn-secondary"
                data-bs-dismiss="modal"
              >
                Close
              </button>
              <button type="submit" class="btn btn-primary">Submit</button>
            </div>
          </div>
        </form>
        <form method="post" @submit.prevent="login" v-else>
          <div class="modal-body">
            <Notification :message="error" v-if="error" />
            <div class="mb-3 row">
              <label for="inputEmail" class="col-sm-2 col-form-label"
                >Email</label
              >
              <div class="col-sm-10">
                <input
                  type="text"
                  class="form-control"
                  id="inputEmail"
                  name="email"
                  v-model="email"
                />
              </div>
            </div>
            <div class="mb-3 row">
              <label for="inputPassword" class="col-sm-2 col-form-label"
                >Password</label
              >
              <div class="col-sm-10">
                <input
                  type="password"
                  class="form-control"
                  id="inputPassword"
                  name="password"
                  v-model="password"
                />
              </div>
            </div>
          </div>
          <div class="modal-footer justify-content-between">
            <button
              type="button"
              class="btn btn-success"
              @click="isLogin = !isLogin"
            >
              Register
            </button>
            <div class="">
              <button
                type="button"
                class="btn btn-secondary"
                data-bs-dismiss="modal"
              >
                Close
              </button>
              <button type="submit" class="btn btn-primary">Submit</button>
            </div>
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
      name: "",
      nik: "",
      phone: "",
      email: "",
      password: "",
      error: null,
    };
  },

  methods: {
    async register() {
      try {
        await this.$axios.post("register", {
          name: this.name,
          email: this.email,
          password: this.password,
          phone: this.phone,
          nik: this.nik,
        });
        await this.$auth.loginWith("local", {
          data: {
            email: this.email,
            password: this.password,
          },
        });
        this.$router.go();
      } catch (e) {
        this.error = e.response.data.data.message;
      }
    },
    async login() {
      try {
        // await this.$axios.$post("login", {
        //   data: {
        //     email: this.email,
        //     password: this.password,
        //   },
        // });
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
