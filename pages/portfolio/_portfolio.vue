<template>
  <div id="page" class="mt-8">
    <div class="title mb-4">
      <h1 class="font-weight-bold">{{ portfolio.head }}</h1>
      <div class="size_create">
        <h6>
          <span class="font-weight-bold">size :</span> {{ portfolio.size }}
        </h6>
        <h6>
          <span class="font-weight-bold">create :</span> {{ portfolio.create }}
        </h6>
      </div>
    </div>
    <!-- รูป เท่ากับ 1 -->
    <div class="flex_img" v-if="portfolio.images.length === 1">
      <figure v-for="image in portfolio.images" :key="image.id">
        <img
          :src="require(`@/assets/images/portfolioDetail/${image.name}`)"
          :alt="portfolio.head"
          class="line_frame"
        />
      </figure>
    </div>
    <!-- end รูป เท่ากับ 1 -->

    <!-- รูป มากกว่า 1 -->
    <div class="grid_img" v-else>
      <figure v-for="image in portfolio.images" :key="image.id">
        <img
          :src="require(`@/assets/images/portfolioDetail/${image.name}`)"
          :alt="portfolio.head"
          class="line_frame"
        />
      </figure>
    </div>
    <!-- end รูป มากกว่า 1 -->
    <h6>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque commodi
      vitae, nostrum quia fugit obcaecati quibusdam nisi vero voluptate qui
      minima velit earum natus aut illum doloremque iure, libero laudantium.
    </h6>
    <h2>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Magni pariatur
      porro iusto, nostrum delectus voluptas iure tempora soluta minus in, ipsam
      vero dignissimos perferendis, atque voluptatem placeat. Dolorem, ipsum
      maiores.
    </h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      details: [
        {
          id: 1,
          head: "Media Kit",
          size: "width 29 cm. x height 23 cm.",
          create: "November 2011",
          images: [{ name: "detail1.jpg" }, { name: "detail2.jpg" }],
          detail:
            "It is a print media for sale. Have sales staff bring this media to sell booths to entrepreneurs. This exhibition will be held every year at BITEC Bangna.",
          name: "port1.jpg",
          to: "Media-Kit",
        },
        {
          id: 2,
          head: "Light Box",
          size: "width 152 cm. x height 91.5 cm.",
          create: "May 2011",
          images: [{ name: "detail3.jpg" }, { name: "detail4.jpg" }],
          detail:
            "Light box sign located in front of the elephant building To indicate that the company has been stationed in front of the elephant building",
          name: "port2.jpg",
          to: "Light-Box",
        },
        {
          id: 3,
          head: "Advertisement The Metropolis",
          size: "width 33.6 cm. x height 25.4 cm.",
          create: "October 2015",
          images: [{ name: "detail5.jpg" }],
          detail:
            "Luxury condo in Bangna area To promote the condo, it has been posted in many media such as newspapers, expressway signs, vinyl signs, brochures.",
          name: "port3.jpg",
          to: "Advertisement-The-Metropolis",
        },
        {
          id: 4,
          head: "Advertisement NARA 9",
          size: "width 29.7 cm. x height 14 cm.",
          create: "November 2015",
          images: [{ name: "detail6.jpg" }, { name: "detail7.jpg" }],
          detail:
            "Luxury condo on Narathiwas-Sathorn road The design of this publication Want to look elegant and elegant Emphasizing on clean and comfortable color tones",
          name: "port4.jpg",
          to: "Advertisement-NARA-9",
        },
        {
          id: 5,
          head: "Advertisement Villa Nakarin",
          size: "width 33.6 cm. x height 25.4 cm.",
          create: "October 2015",
          images: [{ name: "detail8.jpg" }],
          detail:
            "Large luxury house Onnut-Ring Road With a simple, spacious design, natural colors are used to look comfortable. Because it is truly a symbol of the backyard style",
          name: "port5.jpg",
          to: "Advertisement-Villa-Nakarin",
        },
        {
          id: 30,
          head: "Baoshi",
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
          detail:
            "Winner Online's baoshi game guide by the game is a bright fantasy, cute design, so the color scheme looks bright. that can be played by all ages",
          name: "port10.jpg",
          to: "Baoshi",
        },
        {
          id: 31,
          head: "Vinil Gdo Online",
          size: "width 2.5m. x height 1m.",
          create: "October 2014",
          images: [
            {
              name: "detail22.jpg",
            },
          ],
          detail:
            "Adventure game by designing, placing the characters to stand out. then use bright colors which is the theme of this game make it look playful and is of interest to people of all ages.",
          name: "port11.jpg",
          to: "Vinil-Gdo-Online",
        },
        {
          id: 32,
          head: "Poster Gdo Online",
          size: "width 58cm. x height 86cm.",
          create: "October 2014",
          images: [
            {
              name: "detail23.jpg",
            },
          ],
          detail:
            "Adventure game by designing, placing the characters to stand out. then use bright colors which is the theme of this game make it look playful and is of interest to people of all ages.",
          name: "port29.jpg",
          to: "Poster-Gdo-Online",
        },
        {
          id: 6,
          head: "Banner Knight Frank Thailand | Real Estate Agents",
          size: "width 1920 px. x height 600 px.",
          create: "May 2019",
          images: [{ name: "detail9.jpg" }],
          detail:
            "Knight Frank Thailand Banner. It is designed to reflect the search for personnel in various positions. To join us In which the color is red That is a symbol of Knight Frank.",
          name: "port6.jpg",
          to: "Banner-Knight-Frank-Thailand-Real-Estate-Agents",
        },
        {
          id: 7,
          head: "Banner Mitsubishi",
          size: "width 1920 px. x height 600 px.",
          create: "February 2019",
          images: [{ name: "detail10.jpg" }],
          detail:
            "The design will focus on comfort. Natural energy The power that loves the world, there is no pollution, so use colors that look comfortable and clean.",
          name: "port7.jpg",
          to: "Banner-Mitsubishi",
        },
        {
          id: 8,
          head: "Banner CBRE",
          size: "width 960 px. x height 3500 px.",
          create: "July 2019",
          images: [{ name: "detail11.jpg" }],
          detail:
            "The design will focus on green. Which is a symbol of cbre and uses images related to job applications By focusing on various manners to look interesting",
          name: "port8.jpg",
          to: "Banner-CBRE",
        },
        {
          id: 28,
          head: "Banner KTC",
          size: "width 1920 px. x height 600 px.",
          create: "May 2021",
          images: [{ name: "detail19.jpg" }],
          detail:
            "with a simple design and unique in red Make it look luxurious and powerful. I want it to be comfortable on the eyes. Therefore, use white color to make it look attractive and smooth.",
          name: "port28.jpg",
          to: "Banner-KTC",
        },
        {
          id: 10,
          head: "Luxury condo in the heart of the city",
          size: "width 1000 px. x height 500 px.",
          create: "January 2016",
          images: [
            { name: "detail12.jpg" },
            { name: "detail13.jpg" },
            { name: "detail14.jpg" },
          ],
          detail:
            "knight frank is also a broker to help sell real estate to clients. Which each house and condo Is also luxurious and beautiful as well Therefore designed to be colorful, comfortable to the eyes Suitable for rest And see the beautiful scenery",
          name: "port9.jpg",
          to: "Banner-Luxury",
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
    gap: 3rem;
    img {
      width: auto;
    }
  }
}
</style>