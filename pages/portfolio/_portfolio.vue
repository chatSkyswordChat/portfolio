<template>
  <div style="padding-top: 120px">
    <h1>{{ portfolio.head }}</h1>
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
      printDesigns: [],
    };
  },
  computed: {
    portfolio() {
      const api = (v) => v.to == this.$route.params.portfolio;
      return (this.printDesigns = data.printDesigns.find(api));
    },
  },
};
</script>

<style lang="scss" scoped>
</style>