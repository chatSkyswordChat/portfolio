<template>
  <div style="padding-top: 200px">
    <h1>Data fetched using asyncData</h1>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.title">
        <NuxtLink
          :to="{
            name: 'portfolio-portfolio',
            params: { portfolio: mountain.slug },
          }"
        >
          {{ mountain.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>
<script>
// import axios from "axios";
export default {
  // async asyncData() {
  //   const { data } = await axios.get("https://api.nuxtjs.dev/mountains");
  //   return { mountains: data };
  // },
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
