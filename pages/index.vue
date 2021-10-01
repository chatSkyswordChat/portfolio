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