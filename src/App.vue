<template>
  <div>{{ message }}</div>
  <div><a href="/.auth/login/github">Login</a></div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    this.message = text;
  }
};
</script>