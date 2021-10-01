<template>
  <div>
    <present />
    <favorite />
    <workHistory />
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