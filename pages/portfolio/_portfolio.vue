<template>
  <div id="page" class="my-5">
    <h1>{{ portfolio.head }}</h1>
    <div class="grid_img">
      <figure v-for="image in portfolio.images" :key="image.id">
        <img
          :src="require(`@/assets/images/portfolioDetail/${image.name}`)"
          :alt="portfolio.head"
          class="line_frame"
        />
      </figure>
    </div>
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
          head: "Banner London Property Exhibition",
          size: "width 1000 px. x height 500 px.",
          create: "January 2016",
          images: [{ name: "detail12.jpg" }],
          detail:
            "knight frank is also a broker to help sell real estate to clients. Which each house and condo Is also luxurious and beautiful as well Therefore designed to be colorful, comfortable to the eyes Suitable for rest And see the beautiful scenery",
          name: "port9.jpg",
          to: "Banner-London-Property-Exhibition",
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
  max-width: 76.8rem;
  width: 100%;
  margin: 0 auto;
  .grid_img {
    @include flex_center_center();
    flex-wrap: wrap;
    gap: 3rem;
    img {
      width: auto;
    }
  }
}
</style>