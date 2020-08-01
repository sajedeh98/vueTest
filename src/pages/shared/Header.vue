<template>
  <div>

  <nav class="navbar navbar-expand-lg px3" id="navBar">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#myNav">
      <span class="navbar-icon">
        <i class="fas fa-bars"></i>
      </span>
    </button>
    <div class="collapse navbar-collapse" id="myNav">
      <ul class="navbar-nav mx-auto">
        <li class="nav-item active">
          <router-link to="/" class="nav-link">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/AboutUs" class="nav-link">About Us</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/Products" class="nav-link">Products</router-link>
        </li>
        <li class="nav-item" v-if="IsUserAuthenticated">
          <router-link to="/ShopCart" class="nav-link">Shop</router-link>
        </li>
      </ul>
      <div class="account-nav d-lg">
        <ul class="navbar-nav mx-auto" v-if="!IsUserAuthenticated">
          <li>
            <router-link to="/Login" class="nav-item">Login</router-link>/
          </li>
        <li>
            <router-link to="/Register" class="nav-item">Register</router-link>
        </li>
        </ul>
            <ul class="navbar-nav mx-auto" v-else>
          <li>
            <a href="#" class="nav-item">
              {{UserFullName}} Welcom!!
            </a>/
          </li>
        <li>
          <a class="nav-item" style="cursor:pointer" @click="SignOutUser()">
            Sign Out
          </a>
        </li>
        </ul>
      </div>
      <!--end Socials-->
    </div>
  </nav>
  <!-- end nav element -->

  </div>
</template>

<script>
export default {
  computed: {
    IsUserAuthenticated() {
      return this.$store.getters.IsUserAuthenticated;
    },
    UserFullName() {
      return this.$store.getters.GetUserFullName;
    }
  },
  methods: {
    CheckForLogin() {
      this.$store.dispatch("CheckForLogin");
    },
    SignOutUser() {
      this.$store.dispatch("SignOutUser");
    }
  },
  created() {
    this.CheckForLogin();
  }
};
</script>
