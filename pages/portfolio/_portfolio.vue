<template>
  <div>
    <section id="page" class="mt-8">
      <div class="title mb-4">
        <h1 class="font-weight-bold" style="line-height: 2.8rem">
          {{ portfolio.head }}
        </h1>
        <div class="size_create">
          <h6>
            <span class="font-weight-bold">size :</span> {{ portfolio.size }}
          </h6>
          <h6>
            <span class="font-weight-bold">create :</span>
            {{ portfolio.create }}
          </h6>
        </div>
      </div>

      <div
        class="flex_img mb-4"
        v-if="portfolio.images.length === 1 || portfolio.images.length >= 3"
      >
        <figure v-for="image in portfolio.images" :key="image.id">
          <img
            :src="require(`@/assets/images/portfolioDetail/${image.name}`)"
            :alt="portfolio.head"
            class="line_frame"
          />
        </figure>
      </div>

      <div class="grid_img mb-4" v-else>
        <figure v-for="image in portfolio.images" :key="image.id">
          <img
            :src="require(`@/assets/images/portfolioDetail/${image.name}`)"
            :alt="portfolio.head"
            class="line_frame"
          />
        </figure>
      </div>

      <h6 class="mb-4">
        <span class="font-weight-bold">Detail :</span> {{ portfolio.detail }}
      </h6>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      details: [
        {
          head: "Media Kit",
          size: "width 29 cm. x height 23 cm.",
          create: "November 2011",
          images: [{ name: "detail1.jpg" }, { name: "detail2.jpg" }],
          detail: `It is a print media for sale. Have sales staff bring 
          this media to sell booths to entrepreneurs. This exhibition will be held every year at BITEC Bangna.`,
          to: "Media-Kit",
        },
        {
          head: "Light Box",
          size: "width 152 cm. x height 91.5 cm.",
          create: "May 2011",
          images: [{ name: "detail3.jpg" }, { name: "detail4.jpg" }],
          detail: `Light box sign located in front of the elephant building To indicate that 
            the company has been stationed in front of the elephant building`,
          to: "Light-Box",
        },
        {
          head: "Advertisement The Metropolis",
          size: "width 33.6 cm. x height 25.4 cm.",
          create: "October 2015",
          images: [{ name: "detail5.jpg" }],
          detail: `Luxury condo in Bangna area To promote the condo, it has been posted in 
            many media such as newspapers, expressway signs, vinyl signs, brochures.`,
          to: "Advertisement-The-Metropolis",
        },
        {
          head: "Advertisement NARA 9",
          size: "width 29.7 cm. x height 14 cm.",
          create: "November 2015",
          images: [{ name: "detail6.jpg" }, { name: "detail7.jpg" }],
          detail: `Luxury condo on Narathiwas-Sathorn road The design of this publication want to 
            look elegant and elegant Emphasizing on clean and comfortable color tones`,
          name: "port4.jpg",
          to: "Advertisement-NARA-9",
        },
        {
          head: "Advertisement Villa Nakarin",
          size: "width 33.6 cm. x height 25.4 cm.",
          create: "October 2015",
          images: [{ name: "detail8.jpg" }],
          detail: `Large luxury house Onnut-Ring Road With a simple, spacious design, natural 
            colors are used to look comfortable. Because it is truly a symbol of the backyard style`,
          to: "Advertisement-Villa-Nakarin",
        },
        {
          head: "Guide Baoshi",
          size: "width 21 cm. x height 14.8 cm.",
          create: "October 2015",
          images: [
            {
              name: "detail20.jpg",
            },
            {
              name: "detail21.jpg",
            },
          ],
          detail: `Winner Online's baoshi game guide by the game is a bright 
          fantasy, cute design, so the color scheme looks bright. that can be played by all ages`,
          to: "Guide-Baoshi",
        },
        {
          head: "Vinil Gdo Online",
          size: "width 2.5m. x height 1m.",
          create: "October 2014",
          images: [
            {
              name: "detail22.jpg",
            },
          ],
          detail: `Adventure game by designing, placing the characters to stand out. then use bright colors 
            which is the theme of this game make it look playful and is of interest to people of all ages.`,
          to: "Vinil-Gdo-Online",
        },
        {
          head: "Poster Gdo Online",
          size: "width 58cm. x height 86cm.",
          create: "October 2014",
          images: [
            {
              name: "detail23.jpg",
            },
          ],
          detail: `Adventure game by designing, placing the characters to stand out. 
            then use bright colors which is the theme of this game make it look playful and is of 
            interest to people of all ages.`,
          to: "Poster-Gdo-Online",
        },
        {
          head: "Banner Knight Frank Thailand | Real Estate Agents",
          size: "width 1920 px. x height 600 px.",
          create: "May 2019",
          images: [{ name: "detail9.jpg" }],
          detail: `Knight Frank Thailand Banner. It is designed to reflect the search for personnel in various positions. 
            To join us In which the color is red That is a symbol of Knight Frank.`,
          to: "Banner-Knight-Frank-Thailand-Real-Estate-Agents",
        },
        {
          head: "Banner Mitsubishi",
          size: "width 1920 px. x height 600 px.",
          create: "February 2019",
          images: [{ name: "detail10.jpg" }],
          detail: `The design will focus on comfort. Natural energy The power that loves 
          the world, there is no pollution, so use colors that look comfortable and clean.`,
          to: "Banner-Mitsubishi",
        },
        {
          head: "Banner CBRE",
          size: "width 960 px. x height 3500 px.",
          create: "July 2019",
          images: [{ name: "detail11.jpg" }],
          detail: `The design will focus on green. Which is a symbol of cbre and uses images related to 
            job applications By focusing on various manners to look interesting`,
          to: "Banner-CBRE",
        },
        {
          head: "Banner KTC",
          size: "width 1920 px. x height 600 px.",
          create: "May 2021",
          images: [{ name: "detail19.jpg" }],
          detail: `with a simple design and unique in red Make it look luxurious and powerful. 
          I want it to be comfortable on the eyes. Therefore, use white color to make it look attractive and smooth.`,
          to: "Banner-KTC",
        },
        {
          head: "Luxury condo in the heart of the city",
          size: "width 1000 px. x height 500 px.",
          create: "January 2016",
          images: [
            { name: "detail12.jpg" },
            { name: "detail13.jpg" },
            { name: "detail14.jpg" },
          ],
          detail: `knight frank is also a broker to help sell real estate to clients.
           Which each house and condo Is also luxurious and beautiful as well Therefore designed to be colorful, 
            comfortable to the eyes Suitable for rest And see the beautiful scenery`,
          to: "Banner-Luxury",
        },
        {
          head: "Direct Mail Gift Premium",
          size: "width 960 px. x height 3100 px.",
          create: "October 2018",
          images: [{ name: "detail15.jpg" }],
          detail: `The design concept is Give to the people we love By 
          using colors that are comfortable on the eyes, off the pastel line with a simple arrangement. 
          Make it look more premium and attractive.`,
          to: "Direct-Mail-Gift-Premium",
        },
        {
          head: "Direct Mail Great Promotion",
          size: "width 960 px. x height 3100 px.",
          create: "December 2018",
          images: [{ name: "detail16.jpg" }],
          detail: `The most valuable promotion of Icon Ideas with a design that 
          looks comfortable on the eyes. Use pastel tones to look cute and interesting to give to your loved ones.`,
          to: "Direct-Mail-Great-Promotion",
        },
        {
          head: "Design Jobbkk Application",
          size: "na",
          create: "January 2020",
          images: [
            { name: "detail17.jpg" },
            { name: "detail18.jpg" },
            { name: "detail24.jpg" },
            { name: "detail25.jpg" },
          ],
          detail: `Design a jobbkk aplication with adobe xd. The color 
          scheme used is red, white and gray with wireframe, prototype, varidate.`,
          to: "Design-Jobbkk-Application",
        },
      ],
    };
  },
  computed: {
    portfolio() {
      return this.details.find((v) => v.to == this.$route.params.portfolio);
    },
  },
  mounted() {
    const menuPortfolio = document.querySelectorAll(".btn_menu")[2];
    menuPortfolio.classList.add("active");

    const menuMobiles = document
      .querySelector(".v-item-group")
      .querySelectorAll(".btn_menu")[2];
    menuMobiles.classList.add("active");
  },
};
</script>

<style lang="scss" scoped>
#page {
  max-width: 96rem;
  width: 100%;
  margin: 0 auto;
  .title {
    @include flex_start_between();
    gap: 1.6rem;
    .size_create {
      @include flex_start_end();
      flex-direction: column;
      flex-shrink: 0;
      @include responsive_xs() {
        @include flex_start_start();
      }
    }
    @include responsive_xs() {
      flex-direction: column;
    }
  }
  .grid_img {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(45rem, 1fr));
    grid-gap: 3rem;
    @include responsive_xs() {
      grid-template-columns: 1fr;
    }

    img {
      width: auto;
    }
  }
  .flex_img {
    @include flex_center_center();
    flex-direction: column;
    gap: 3rem;
    img {
      width: auto;
    }
  }
}
</style>