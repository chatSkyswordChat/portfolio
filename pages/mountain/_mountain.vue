<template>
  <div style="padding-top: 120px">
    <h1>{{ title }}</h1>
    <img :src="image" alt="" />
    <h6>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque commodi
      vitae, nostrum quia fugit obcaecati quibusdam nisi vero voluptate qui
      minima velit earum natus aut illum doloremque iure, libero laudantium.
    </h6>
    <h2>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Magni pariatur
      porro iusto, nostrum delectus voluptas iure tempora soluta minus in, ipsam
      vero dignissimos perferendis, atque voluptatem placeat. Dolorem, ipsum
      maiores.
    </h2>
  </div>
</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const data = await $axios.$get(
      `https://api.nuxtjs.dev/mountains/${params.mountain}`
    );
    return data;
  },
};
</script>

<style lang="scss" scoped>
</style>
