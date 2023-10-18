<template>
  <header class="header">
    <img src="@/assets/logo%20(white).svg" alt="logo" class="logo" />
    <span class="logo-text">I was crazy once</span>
    <div class="user-info" v-if="loggedIn">
      <div class="avatar" :style="{ backgroundColor: avatarColor }"></div>
      <div class="user-name">{{ full_name }}</div>
    </div>
    <button class="login-button" @click="handleLoginLogout">{{ loggedIn ? 'LOGOUT' : 'LOGIN' }}</button>
  </header>
</template>
<script>
export default {
  data() {
    return {
      loggedIn: false,
      user: {
        name: "Brendons",
        surname: "Liflands",
        code: "IT21009",
      },
      avatarColor: this.getRandomColor(),
    };
  },
  computed: {
    full_name() {
      return `${this.user.name} ${this.user.surname}`;
    },
  },
  methods: {
    handleLoginLogout() {
      if (this.loggedIn) {
        const confirmLogout = window.confirm("Do you want to log out?");
        if (confirmLogout) {
          this.logout();
        }
      } else {
        const confirmLogin = window.confirm("Do you want to log in?");
        if (confirmLogin) {
          this.login();
        }
      }
    },
    login() {
      this.loggedIn = true;
      this.avatarColor = this.getRandomColor();
      this.$emit("login");
    },
    logout() {
      this.loggedIn = false;
      this.$emit("logout");
    },
    getRandomColor() {
      const letters = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    },
  },
};
</script>

<style>


</style>