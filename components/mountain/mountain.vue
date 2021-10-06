<template>
  <div>
    <div v-for="mountain in mountains" :key="mountain.id">
      <nuxt-link
        :to="{
          name: 'mountain-mountain',
          params: { mountain: mountain.slug },
        }"
      >
        <h1>{{ mountain.title }}</h1>
      </nuxt-link>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      mountains: [],
    };
  },
  async fetch() {
    this.mountains = await fetch("https://api.nuxtjs.dev/mountains").then(
      (res) => res.json()
    );
  },
};
</script>
