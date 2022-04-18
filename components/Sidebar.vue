<template>
  <div
    class="sidebar d-flex flex-column align-items-center justify-content-between"
  >
    <div class="brand-logo">
      <img src="~/assets/logo.svg" alt="" />
    </div>
    <div class="nav d-flex flex-column">
      <nuxt-link class="d-flex justify-content-center" to="/">
        <img class="active" src="~/assets/icon_hospital.svg" alt="" />
      </nuxt-link>
      <nuxt-link class="d-flex justify-content-center" to="/book">
        <img src="~/assets/icon_bookmark.svg" alt="" />
      </nuxt-link>
      <nuxt-link class="d-flex justify-content-center" to="/profile">
        <img src="~/assets/icon_profile.svg" alt="" />
      </nuxt-link>
    </div>
    <div class="setting d-flex flex-column">
      <img src="~/assets/icon_setting.svg" alt="" />
      <img src="~/assets/icon_about.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    console.log($(".nav nuxt-link"));
    $(".nav a img").on("click", function () {
      $(".nav").find(".active").removeClass("active");
      $(this).addClass("active");
    });
  },
};
</script>
