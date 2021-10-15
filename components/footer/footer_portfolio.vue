<template>
  <div id="footer" class="color_secondary bg_primary calc pa-4">
    <v-container class="pa-0">
      <v-row>
        <v-col col="12" md="8" sm="12">
          <h3 class="set_address mb-2">
            <div class="footer_icon bg_info">
              <font-awesome-icon
                class="font_superText"
                :icon="['fas', 'user']"
              />
            </div>
            <div>
              <span class="font-weight-bold">Name : </span>Chatthong
              Hongwisuthikul
            </div>
          </h3>

          <h6 class="set_address mb-2 font_superText">
            <div class="footer_icon bg_warning">
              <font-awesome-icon
                class="font_superText"
                :icon="['fas', 'map-marker-alt']"
              />
            </div>
            <div>
              <span class="font-weight-bold">Address :</span> 447 Lat Phrao 109
              Road, Khlong Chan Subdistrict, Bang Kapi District, Bangkok 10240
            </div>
          </h6>

          <h6 class="set_address mb-2 font_superText">
            <div class="footer_icon bg_success">
              <font-awesome-icon
                class="font_superText"
                :icon="['fas', 'mobile-alt']"
              />
            </div>
            <div><span class="font-weight-bold">Tel :</span> 08-9762-0645</div>
          </h6>

          <h6 class="set_address font_superText">
            <div class="footer_icon bg_link">
              <font-awesome-icon
                class="font_superText"
                :icon="['fas', 'envelope']"
              />
            </div>
            <div>
              <span class="font-weight-bold">E-mail :</span>
              dynastystrike@gmail.com
            </div>
          </h6>
        </v-col>

        <v-col col="12" md="4" sm="12">
          <h3 class="font-weight-bold mb-4">Social</h3>
          <h6 class="set_address mb-2">
            <div class="footer_icon" style="background: #1877f2">
              <font-awesome-icon
                class="font_superText"
                :icon="['fab', 'facebook-f']"
              />
            </div>
            <div>
              <a
                href="https://www.facebook.com/chatthong.hongwisuthikul"
                target="_blank"
              >
                Chatthong Hongwisuthikul</a
              >
            </div>
          </h6>
          <h6 class="set_address mb-2">
            <div class="footer_icon" style="background: #07b53b">
              <font-awesome-icon
                class="font_superText"
                :icon="['fab', 'line']"
              />
            </div>
            <div>chat_skysword</div>
          </h6>
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
  a {
    color: $color_secondary;
    &:hover {
      text-decoration: underline;
    }
  }
}
</style>