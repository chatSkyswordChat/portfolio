<template>
  <div id="footer" class="color_secondary bg_primary calc pa-4">
    <v-container class="pa-0">
      <v-row>
        <v-col col="12" class="text-center">
          <h3 class="font_subHead mb-2 font-weight-medium">
            Chatthong Hongwisuthikul
          </h3>

          <h6>
            Address : 447 Lat Phrao 109 Road, Khlong Chan Subdistrict, Bang Kapi
            District, Bangkok 10240
          </h6>
          <h6>Tel : 08-9762-0645</h6>
          <h6>E-mail : dynastystrike@gmail.com</h6>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#footer {
  .set_address {
    @include flex_center_start();
    gap: 1.6rem;
    .footer_icon {
      width: 3rem;
      height: 3rem;
      border-radius: 50%;
      @include flex_center_center();
      flex-shrink: 0;
    }
  }
}
</style>