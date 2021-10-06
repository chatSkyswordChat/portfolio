<template>
  <section id="portfolio" class="py-4">
    <v-tabs background-color="white" color="red darken-2" left>
      <v-tab>Print Media</v-tab>
      <v-tab>Banner</v-tab>
      <v-tab>Logo</v-tab>
      <v-tab>Web Design</v-tab>

      <v-tab-item v-for="tab in 4" :key="tab.id" class="mt-4">
        <section class="portfolio">
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

      <!-- <v-tab-item v-for="tab in 1" :key="tab.id">
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
      </v-tab-item> -->

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
      // printDesigns: [
      //   {
      //     id: 1,
      //     head: "Media Kit",
      //     size: "width 29 cm. x height 23 cm.",
      //     create: "November 2011",
      //     imgaes: [{ name: "detail1.jpg" }, { name: "detail2.jpg" }],
      //     detail:
      //       "It is a print media for sale. Have sales staff bring this media to sell booths to entrepreneurs. This exhibition will be held every year at BITEC Bangna.",
      //     name: "port1.jpg",
      //     to: "Media-Kit",
      //   },
      //   {
      //     id: 2,
      //     head: "Light Box",
      //     size: "width 152 cm. x height 91.5 cm.",
      //     create: "May 2011",
      //     imgaes: [{ name: "detail3.jpg" }, { name: "detail4.jpg" }],
      //     detail:
      //       "Light box sign located in front of the elephant building To indicate that the company has been stationed in front of the elephant building",
      //     name: "port2.jpg",
      //     to: "Light-Box",
      //   },
      //   {
      //     id: 3,
      //     head: "Advertisement The Metropolis",
      //     size: "width 33.6 cm. x height 25.4 cm.",
      //     create: "October 2015",
      //     imgaes: [{ name: "detail5.jpg" }],
      //     detail:
      //       "Luxury condo in Bangna area To promote the condo, it has been posted in many media such as newspapers, expressway signs, vinyl signs, brochures.",
      //     name: "port3.jpg",
      //     to: "Advertisement-The-Metropolis",
      //   },
      //   {
      //     id: 4,
      //     head: "Advertisement NARA 9",
      //     size: "width 29.7 cm. x height 14 cm.",
      //     create: "November 2015",
      //     imgaes: [{ name: "detail6.jpg" }, { name: "detail7.jpg" }],
      //     detail:
      //       "Luxury condo on Narathiwas-Sathorn road The design of this publication Want to look elegant and elegant Emphasizing on clean and comfortable color tones",
      //     name: "port4.jpg",
      //     to: "Advertisement-NARA-9",
      //   },
      //   {
      //     id: 5,
      //     head: "Advertisement Villa Nakarin",
      //     size: "width 33.6 cm. x height 25.4 cm.",
      //     create: "October 2015",
      //     imgaes: [{ name: "detail8.jpg" }],
      //     detail:
      //       "Large luxury house Onnut-Ring Road With a simple, spacious design, natural colors are used to look comfortable. Because it is truly a symbol of the backyard style",
      //     name: "port5.jpg",
      //     to: "Advertisement-Villa-Nakarin",
      //   },
      // ],
      // bannerDesigns: [],
      printDesigns: [],
    };
  },
  async mounted() {
    this.printDesigns = await data.printDesigns;
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