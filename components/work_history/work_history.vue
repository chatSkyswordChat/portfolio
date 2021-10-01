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
  async mounted() {
    const AOS = await import("aos");
    AOS.init();
  },
};
</script>

<style lang="scss" scoped>
#work_history {
  position: relative;
  .bg_my img {
    height: 120vh;
    object-fit: cover;
    @include responsive_md() {
      height: 150vh;
    }
    @include responsive_xxxs() {
      height: 160vh;
    }
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

<style lang="scss">
@include responsive_sm() {
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse):before {
    left: 0;
    background: inherit;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before),
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after {
    flex-direction: column-reverse;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after),
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before {
    flex-direction: column-reverse;
  }
  .v-timeline-item__divider {
    display: none;
  }
  .v-timeline-item__opposite {
    max-width: 100%;
    margin-bottom: 1.6rem;
  }
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before)
    .v-timeline-item__opposite,
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after
    .v-timeline-item__opposite {
    text-align: left;
    width: 100%;
  }
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after)
    .v-timeline-item__opposite,
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before
    .v-timeline-item__opposite {
    text-align: left;
    width: 100%;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before)
    .v-timeline-item__body,
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after
    .v-timeline-item__body {
    max-width: 100%;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after)
    .v-timeline-item__body,
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before
    .v-timeline-item__body {
    max-width: 100%;
  }
  .v-timeline-item__body > .v-card:not(.v-card--flat):before,
  .v-timeline-item__body > .v-card:not(.v-card--flat):after {
    border-top: 0;
    border-bottom: 0;
  }
}
</style>