<template>
  <div
    class="sidebar d-flex flex-column align-items-center justify-content-between sticky-top"
  >
    <div class="brand-logo">
      <img src="~/assets/logo.svg" alt="" />
    </div>
    <div class="nav d-flex flex-column">
      <nuxt-link class="d-flex justify-content-center" to="/">
        <img src="~/assets/icon_hospital.png" alt="" />
      </nuxt-link>
      <nuxt-link
        class="d-flex justify-content-center"
        to="/book"
        v-if="!isAuthenticated"
      >
        <img src="~/assets/icon_bookmark.png" alt="" />
      </nuxt-link>
      <nuxt-link
        class="d-flex justify-content-center"
        to="/profile"
        v-if="isAuthenticated"
      >
        <img src="~/assets/icon_profile.png" alt="" />
      </nuxt-link>
    </div>
    <div class="setting d-flex flex-column">
      <img src="~/assets/icon_setting.svg" alt="" @click="$auth.logout()" />
      <img src="~/assets/icon_about.svg" alt="" />
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters(["isAuthenticated", "loggedInUser"]),
  },
};
</script>

<style>
/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  background-color: rgba(255, 255, 255, 0.5);
  padding: 1rem;
  border-radius: 1rem;
}
</style>
