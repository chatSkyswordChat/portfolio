<template>
  <section id="portfolio" class="py-4">
    <v-tabs background-color="white" color="red darken-2" left>
      <v-tab class="px-0 font_text width_tab">Print Media</v-tab>
      <v-tab class="px-0 font_text width_tab">Banner</v-tab>
      <v-tab class="px-0 font_text width_tab">Logo</v-tab>
      <v-tab class="px-0 font_text width_tab">Web Design</v-tab>

      <v-tab-item v-for="tab in 1" :key="tab.id" class="mt-4">
        <section class="portfolio mb-4">
          <div
            v-for="printDesign in printDesigns"
            :key="printDesign.id"
            class="frame elevation-5"
          >
            <nuxt-link
              :to="{
                name: 'portfolio-portfolio',
                params: { portfolio: printDesign.to },
              }"
              target="_blank"
            >
              <figure>
                <img
                  :src="
                    require(`@/assets/images/portfolio/${printDesign.name}`)
                  "
                  :lazy-src="printDesign.name"
                  alt
                />
              </figure>
              <div class="detail bg_disabled pa-4">
                <p class="mb-4 color_text">{{ printDesign.detail }}</p>
                <v-btn class="font_small bg_primary color_secondary read"
                  >read more</v-btn
                >
              </div>
            </nuxt-link>
          </div>
        </section>
      </v-tab-item>

      <v-tab-item v-for="tab in 1" :key="tab.id" class="mt-4">
        <section class="portfolio mb-4">
          <div
            v-for="bannerDesign in bannerDesigns"
            :key="bannerDesign.id"
            class="frame elevation-5"
          >
            <nuxt-link
              :to="{
                name: 'portfolio-portfolio',
                params: { portfolio: bannerDesign.to },
              }"
              target="_blank"
            >
              <figure>
                <img
                  :src="
                    require(`@/assets/images/portfolio/${bannerDesign.name}`)
                  "
                  :lazy-src="bannerDesign.name"
                  alt
                />
              </figure>
              <div class="detail bg_disabled pa-4">
                <p class="mb-4 color_text">{{ bannerDesign.detail }}</p>
                <v-btn class="font_small bg_primary color_secondary read"
                  >read more</v-btn
                >
              </div>
            </nuxt-link>
          </div>
        </section>
      </v-tab-item>

      <v-tab-item v-for="tab in 1" :key="tab.id" class="mt-4">
        <section class="logo mb-4 px-4">
          <div
            v-for="logoDesign in logoDesigns"
            :key="logoDesign.id"
            class="frame elevation-5"
          >
            <figure>
              <img
                class="pa-4"
                :src="require(`@/assets/images/portfolio/${logoDesign.name}`)"
                :lazy-src="logoDesign.name"
                alt
              />
            </figure>
          </div>
        </section>
      </v-tab-item>

      <!-- <v-tab-item v-for="protfolioThree in 1" :key="protfolioThree.id">
        <tabThree />
      </v-tab-item>

      <v-tab-item v-for="protfolioFour in 1" :key="protfolioFour.id">
        <tabFour />
      </v-tab-item> -->
    </v-tabs>
  </section>
</template>

<script>
import data from "@/data/data.json";
export default {
  data() {
    return {
      printDesigns: [],
      bannerDesigns: [],
      logoDesigns: [],
    };
  },
  async mounted() {
    this.printDesigns = await data.printDesigns;
    this.bannerDesigns = await data.bannerDesigns;
    this.logoDesigns = await data.logoDesigns;
  },
};
</script>

<style lang="scss" scoped>
#portfolio {
  .width_tab {
    min-width: 12rem;
    &.v-tab--active {
      background: $color_primary;
      color: $color_secondary;
    }
  }
  .portfolio {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(28rem, 1fr));
    grid-gap: 1.6rem;
    .frame {
      display: flex;
      overflow: hidden;
      border-radius: 0.5rem 0.5rem 0 0;
    }
    a {
      display: flex;
      flex-direction: column;
      width: 100%;
    }
    figure {
      display: flex;
    }
    .detail {
      @include flex_end_between();
      flex-direction: column;
      height: 100%;
      p {
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
      .read {
        display: inline-block;
      }
    }
    img {
      max-width: 100%;
      object-fit: cover;
    }
  }
  .logo {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
    grid-gap: 3rem;
    .frame {
      border-radius: 0.5rem 0.5rem 0 0;
    }
    figure {
      display: flex;
      img {
        @extend .frame;
      }
    }
  }
}
</style>

<style lang="scss">
.v-tabs:not(.v-tabs--vertical).v-tabs--right
  > .v-slide-group--is-overflowing.v-tabs-bar--is-mobile:not(.v-slide-group--has-affixes)
  .v-slide-group__next,
.v-tabs:not(.v-tabs--vertical):not(.v-tabs--right)
  > .v-slide-group--is-overflowing.v-tabs-bar--is-mobile:not(.v-slide-group--has-affixes)
  .v-slide-group__prev {
  display: none !important;
}
.v-tabs-slider-wrapper {
  height: 0.3rem !important;
}
.v-tabs-slider {
  background-color: #9c0202 !important;
}
</style>