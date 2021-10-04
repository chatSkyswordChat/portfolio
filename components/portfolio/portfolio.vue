<template>
  <section id="portfolio" class="py-4">
    <v-tabs background-color="white" color="red darken-2" left>
      <v-tab>Print Media</v-tab>
      <v-tab>Banner</v-tab>
      <v-tab>Logo</v-tab>
      <v-tab>Web Design</v-tab>

      <v-tab-item v-for="tab in 1" :key="tab.id" class="mt-4">
        <div v-for="portfolio in portfolios" :key="portfolio.id">
          <section class="portfolio">
            <div
              v-for="printDesign in portfolio.printDesigns"
              :key="printDesign.id"
              class="frame elevation-5"
            >
              <nuxt-link :to="printDesign.to" target="_blank">
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
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Perferendis recusandae possimus dolorem maiores alias
                    expedita? Ipsum provident fuga quisquam perferendis
                    laudantium commodi voluptas iste quibusdam! Sint neque nemo
                    tempore maiores?
                  </p>
                </div>
              </nuxt-link>
            </div>
          </section>
        </div>
      </v-tab-item>

      <v-tab-item v-for="tab in 1" :key="tab.id">
        <div v-for="portfolio in portfolios" :key="portfolio.id">
          <section class="portfolio">
            <div
              v-for="bannerDesign in portfolio.bannerDesigns"
              :key="bannerDesign.id"
              class="frame elevation-5"
            >
              <nuxt-link :to="bannerDesign.to" target="_blank">
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
                    expedita? Ipsum provident fuga quisquam perferendis
                    laudantium commodi voluptas iste quibusdam! Sint neque nemo
                    tempore maiores?
                  </p>
                </div>
              </nuxt-link>
            </div>
          </section>
        </div>
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
import data from "@/data/data";
export default {
  data() {
    return {
      portfolios: [],
    };
  },
  async mounted() {
    this.portfolios = await data.portfolios;
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
      // .detail {
      // }
    }
    a {
      width: 100%;
    }
    figure {
      display: flex;
    }
    img {
      max-width: 100%;
      object-fit: cover;
    }
  }
}
</style>