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
        <v-timeline-item
          v-for="(workHistory, index) in workHistorys"
          :key="index.id"
          class="timeline"
        >
          <template v-slot:opposite>
            <span class="color_secondary font_subHead date">{{
              workHistory.date
            }}</span>
          </template>
          <v-card
            class="elevation-5"
            :data-aos="workHistory.fade"
            :data-aos-duration="workHistory.number"
          >
            <v-card-title
              class="bg_primary font_superText color_secondary py-2 mb-2"
            >
              {{ workHistory.company }}
            </v-card-title>
            <h6 class="font_superText font-weight-bold px-4 mb-2">
              {{ workHistory.position }}
            </h6>
            <v-card-text class="font_text pt-0 detail">
              {{ workHistory.detail }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </div>
  </section>
</template>

<script>
import data from "@/data/data.json";
export default {
  data() {
    return {
      workHistorys: [],
    };
  },
  async beforeMount() {
    this.workHistorys = await data.workHistorys;

    const workHistory = () => {
      if (this.$route.path === "/") {
        this.workHistorys = this.workHistorys.slice(0, 3);
      } else {
        this.workHistorys;
      }
    };

    workHistory();
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
  .bg_my {
    position: absolute;
    width: 100%;
    height: 100%;
    img {
      height: 100%;
      object-fit: cover;
      position: absolute;
    }
  }

  .work_history {
    h2 {
      position: relative;
    }
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
    left: 0 !important;
    background: inherit !important;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before),
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after {
    flex-direction: column-reverse !important;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after),
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before {
    flex-direction: column-reverse !important;
  }
  .v-timeline-item__divider {
    display: none !important;
  }
  .v-timeline-item__opposite {
    max-width: 100% !important;
    margin-bottom: 1.6rem !important;
  }
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before)
    .v-timeline-item__opposite,
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after
    .v-timeline-item__opposite {
    text-align: left !important;
    width: 100% !important;
  }
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after)
    .v-timeline-item__opposite,
  .v-application--is-ltr
    .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before
    .v-timeline-item__opposite {
    text-align: left !important;
    width: 100% !important;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(odd):not(.v-timeline-item--before)
    .v-timeline-item__body,
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--after
    .v-timeline-item__body {
    max-width: 100% !important;
  }
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item:nth-child(even):not(.v-timeline-item--after)
    .v-timeline-item__body,
  .v-timeline:not(.v-timeline--dense):not(.v-timeline--reverse)
    .v-timeline-item--before
    .v-timeline-item__body {
    max-width: 100% !important;
  }
  .v-timeline-item__body > .v-card:not(.v-card--flat):before,
  .v-timeline-item__body > .v-card:not(.v-card--flat):after {
    border-top: 0 !important;
    border-bottom: 0 !important;
  }
}
</style>