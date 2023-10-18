<template>
  <nav class="navigation">
    <button class="sidebutton"  @click="switchPage('home')" :class="{ active: activePage === 'home' }" v-if="loggedIn">FACTS</button>
    <button class="sidebutton"  @click="switchPage('about')" :class="{ active: activePage === 'about' }" v-if="loggedIn">ABOUT ME</button>
  </nav>
</template>


<script>
export default {
  props: {
    loggedIn: Boolean,
    activePage: String,
  },
  methods: {
    switchPage(page) {
      this.$emit('change-page', page);
    },
  },
};
</script>


<style>

</style>