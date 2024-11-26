<script setup>
import GithubCard from "./components/GithubProfile.vue";
</script>

<template>
  <GithubCard userName="danielkellyio" />
  <GithubCard userName="mohammad-jafari-79" />
  <GithubCard userName="adamchainz" />
  <GithubCard userName="adamwathan" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
