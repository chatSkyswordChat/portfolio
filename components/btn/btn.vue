<template>
  <div>
    <button type="button" :class="classButton">{{ btnText }}</button>
    <v-btn color="primary" depressed>ddddddddddd</v-btn>
  </div>
</template>

<script>
export default {
  props: {
    btnText: {
      type: String,
      default: "this is button",
    },
    box_shadow: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    classButton() {
      let shadow;
      if (this.box_shadow) {
        shadow = true;
      }

      return { box_shadow: shadow };
    },
  },
};
</script>

<style lang="scss" scoped>
.box_shadow {
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
}
</style>