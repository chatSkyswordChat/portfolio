<template>
  <div>
    <button type="button" :class="classButton" :style="styleButton">
      {{ btnText }}
    </button>
    <v-btn color="primary" depressed>ddddddddddd</v-btn>
  </div>
</template>

<script>
export default {
  props: {
    btnText: {
      type: String,
      default: "this is button"
    },
    box_shadow: {
      type: Boolean,
      default: false
    },
    btn_red: {
      type: Boolean,
      default: false
    },
    color_white: {
      type: Boolean,
      default: false
    },
    padding: {
      type: String,
      default() {
        return null;
      }
    }
  },
  computed: {
    classButton() {
      let shadow;
      if (this.box_shadow) {
        shadow = true;
      }

      let btnRed;
      if (this.btn_red) {
        btnRed = true;
      }

      let colorWhite;
      if (this.color_white) {
        colorWhite = true;
      }

      return { box_shadow: shadow, btn_red: btnRed, color_white: colorWhite };
    },
    styleButton() {
      let pad = `.5rem 1.5rem`;
      if (this.padding) {
        pad = `${this.padding}rem ${this.padding}rem`;
      }

      return { padding: pad };
    }
  }
};
</script>

<style lang="scss" scoped>
.box_shadow {
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
}
.btn_red {
  background: $color_primary;
}
.color_white {
  color: $color_secondary;
}
</style>
