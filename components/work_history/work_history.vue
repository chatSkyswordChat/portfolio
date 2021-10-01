<template>
  <section id="work_history">
    <figure class="bg_my">
      <picture>
        <source srcset="@/assets/images/home/bg3.webp" type="image/webp" />
        <source srcset="@/assets/images/home/bg3.jpg" type="image/jpg" />
        <img class="calc" src="@/assets/images/home/bg3.jpg" alt="" />
      </picture>
    </figure>

    <div class="work_history py-4">
      <h2 class="font_head color_secondary mb-4">Work History</h2>
      <v-timeline>
        <v-timeline-item v-for="(item, index) in items" :key="index.id">
          <template v-slot:opposite>
            <span class="color_secondary font_subHead date">{{
              item.date
            }}</span>
          </template>
          <v-card
            class="elevation-5"
            :data-aos="item.fade"
            :data-aos-duration="item.number"
          >
            <v-card-title
              class="bg_primary font_superText color_secondary py-2 mb-2"
            >
              {{ item.company }}
            </v-card-title>
            <h6 class="font_superText font-weight-bold px-4 mb-2">
              {{ item.position }}
            </h6>
            <v-card-text class="font_text pt-0 detail">
              {{ item.detail }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          date: "June 2017 to Present",
          company: `บริษัท จัดหางาน จ๊อบบีเคเค ดอท คอม จำกัด`,
          position: "Web Designer",
          detail: `Design website, write Html Css code and make screen to be 
          Responsive, design banner for customers to use the service`,
          fade: "fade-left",
          number: "1000",
        },
        {
          date: "February 2016 to May 2017",
          company: `บริษัท อีซี่วัน ไทย`,
          position: "Web Designer",
          detail: `Website Design Write Html Css Code and Make Responsive Screens, Banner and Logo Design`,
          fade: "fade-right",
          number: "1200",
        },
        {
          date: "September 2015 to February 2016",
          company: `Knight Frank Thailand | Real Estate Agents`,
          position: "Graphic Designer",
          detail: `Design banners, brochures, vinyl banners. Check the work already. To enter the printing process`,
          fade: "fade-left",
          number: "1400",
        },
        {
          date: "September 2012 to September 2015",
          company: `บริษัท วินเนอร์ ออนไลน์ จำกัด`,
          position: "Web Designer",
          detail: `Banner design, media design Design package design, logo, website design and write html css and display the screen responsive`,
          fade: "fade-right",
          number: "1600",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
#work_history {
  position: relative;
  .bg_my img {
    height: 120vh;
    object-fit: cover;
  }
  .work_history {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    .date {
      text-shadow: 0.2rem 0.2rem 0.5rem rgba(0, 0, 0, 0.5);
    }
    .detail {
      line-height: 1.5;
    }
  }
}
</style>