<template>
  <section id="portfolio" class="py-4">
    <v-tabs background-color="white" color="red darken-2" left>
      <v-tab>Print Media</v-tab>
      <v-tab>Banner</v-tab>
      <v-tab>Logo</v-tab>
      <v-tab>Web Design</v-tab>

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

      <v-tab-item v-for="tab in 1" :key="tab.id">
        <section class="portfolio">
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
                <p>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Perferendis recusandae possimus dolorem maiores alias
                  expedita? Ipsum provident fuga quisquam perferendis laudantium
                  commodi voluptas iste quibusdam! Sint neque nemo tempore
                  maiores?
                </p>
              </div>
            </nuxt-link>
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
    };
  },
  async mounted() {
    this.printDesigns = await data.printDesigns;
    this.bannerDesigns = await data.bannerDesigns;
  },
};
</script>

<style lang="scss" scoped>
#portfolio {
  .portfolio {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(28rem, 1fr));
    grid-gap: 1.6rem;
    .frame {
      display: flex;
      overflow: hidden;
    }
    a {
      width: 100%;
    }
    figure {
      display: flex;
    }
    .detail {
      @include flex_start_end();
      flex-direction: column;
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
}
</style>