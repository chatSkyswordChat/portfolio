<template>
  <div>
    <present />
    <favorite />
    <workHistory />
    <h1>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quibusdam eius
      sit, illo dolores explicabo, earum maiores optio itaque sequi eos
      excepturi quas ipsam obcaecati culpa eligendi vel. Iste, ullam?
      Consequatur.
    </h1>
    <h2>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Vitae, sit vero
      qui, debitis molestiae recusandae quo eum culpa dicta aliquid, corrupti
      aperiam ratione ea nesciunt odio alias laboriosam explicabo est?
    </h2>
  </div>
</template>

<script>
export default {
  async mounted() {
    const AOS = await import("aos");
    AOS.init();
  },
};
</script>

<style lang="scss" scoped>
</style>