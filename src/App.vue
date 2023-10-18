<template>
  <div class="app-container">
    <div class="headerbar">
      <HeaderComponent @login="login" @logout="logout" :loggedIn="loggedIn"/>
    </div>
    <main class="content">
      <aside class="sidebar">
      <NavigationComponent @change-page="changePage" :loggedIn="loggedIn"/>
      </aside>
      <div class="page-content">
      <HomeComponent v-if="loggedIn && activePage === 'home'"/>
      <AboutMeComponent v-if="activePage === 'about'"/>
      </div>
    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import NavigationComponent from './components/NavigationComponent.vue';
import HomeComponent from './components/HomeComponent.vue';
import AboutMeComponent from './components/AboutMeComponent.vue';

export default {
  data() {
    return {
      loggedIn: false,
      activePage: 'home',
    };
  },
  components: {
    HeaderComponent,
    NavigationComponent,
    HomeComponent,
    AboutMeComponent,
  },
  methods: {
    login() {
      this.loggedIn = true;
    },
    logout() {
      this.loggedIn = false;
      this.activePage = 'home';
    },
    changePage(page) {
      this.activePage = page;
    },
  },
};
</script>
<style scoped>

</style>

