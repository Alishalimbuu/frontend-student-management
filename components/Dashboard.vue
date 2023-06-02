<template>
  <div>
    <main>
      <section class="d-flex" style="height: 150vh">
        <div class="bg-secondary w-25 pt-5">
          <h3 class="text-info">Student Dashboard</h3>
          <ul style="list-style-type: none">
            <li class="my-3">
              <nuxt-link to="/">Home Page</nuxt-link>
            </li>
            <li class="my-3">
              <nuxt-link to="/dashboard">Dashboard</nuxt-link>
            </li>
            <li class="my-3">
              <nuxt-link to="/profile" @click="fetchProfile">Profile</nuxt-link>
            </li>
            <li class="my-3">
              <nuxt-link to="/rules">Rules & Regulation</nuxt-link>
            </li>
            <li class="my-3">
              <nuxt-link to="/feedback">Feedback & Rating</nuxt-link>
            </li>
            <li class="my-3">
              <nuxt-link to="/message">Message</nuxt-link>
            </li>
            <li class="my-3">
              <a href="#" @click="logOut()">Logout</a>
            </li>
          </ul>
        </div>
        <div class="w-75 pt-5">
          <slot></slot>
        </div>
      </section>
    </main>
    <footer></footer>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "DashboardTemplate",
  methods: {
    ...mapActions(["fetchProfile"]),
    logOut() {
      localStorage.removeItem("user");
      this.$router.push({ name: "home" });
    },
  },
};
</script>

<style scoped>
a {
  color: white;
  text-decoration: none;
  text-align: left;
  font-size: 22px;
  font-family: Times New Roman;
}
</style>
