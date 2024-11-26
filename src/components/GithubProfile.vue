<script setup>
import { ref } from "vue";

const props = defineProps({
  userName: { type: String, Required: true },
});

const user = ref();

fetch(`https://api.github.com/users/${props.userName}`).then(async (res) => {
  const data = await res.json();
  user.value = data;
});
</script>

<template>
  <div v-if="user" class="card card-side bg-base-100 shadow-xl my-2.5">
    <figure>
      <img :src="user.avatar_url" alt="user profile picture" />
    </figure>
    <div class="card-body justify-between">
      <section class="justify-start">
        <h2 class="card-title">{{ user.name }}</h2>
        <h2 class="card-title">
          Followers:
          <p class="font-thin">{{ user.followers }}</p>
        </h2>
        <h2 class="card-title">
          Following:
          <p class="font-thin">{{ user.following }}</p>
        </h2>
      </section>
      <div class="card-actions justify-end">
        <a :href="user.html_url" class="btn btn-primary">Veiw Profile</a>
      </div>
    </div>
  </div>
</template>

<style></style>
