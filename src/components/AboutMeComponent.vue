<template>
  <div class="aboutme">
    <h1>About me</h1>
    <h3>Name: {{ user.name }}</h3>
    <h3>Surname: {{ user.surname }}</h3>
    <h3>Code: {{ user.code }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: "Brendons",
        surname: "Liflands",
        code: "IT21009",
      },
    };
  },
};
</script>
