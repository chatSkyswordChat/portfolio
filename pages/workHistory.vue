<template>
  <div>
    <section id="work_history">
      <figure class="bg_my">
        <picture>
          <source srcset="@/assets/images/home/bg3.webp" type="image/webp" />
          <source srcset="@/assets/images/home/bg3.jpg" type="image/jpg" />
          <img class="calc" src="@/assets/images/home/bg3.jpg" alt="" />
        </picture>
      </figure>

      <div class="work_history py-4">
        <h2 class="font_head color_secondary mb-4 tu">Work History</h2>
        <v-timeline>
          <v-timeline-item
            v-for="(workHistoryAll, index) in workHistoryAlls"
            :key="index.id"
            class="timeline"
          >
            <template v-slot:opposite>
              <span class="color_secondary font_subHead date">{{
                workHistoryAll.date
              }}</span>
            </template>
            <v-card
              class="elevation-5"
              :data-aos="workHistoryAll.fade"
              :data-aos-duration="workHistoryAll.number"
            >
              <v-card-title
                class="bg_primary font_superText color_secondary py-2 mb-2"
              >
                {{ workHistoryAll.company }}
              </v-card-title>
              <h6 class="font_superText font-weight-bold px-4 mb-2">
                {{ workHistoryAll.position }}
              </h6>
              <v-card-text class="font_text pt-0 detail">
                {{ workHistoryAll.detail }}
              </v-card-text>
            </v-card>
          </v-timeline-item>
        </v-timeline>
      </div>
    </section>
  </div>
</template>

<script>
import data from "@/data/data.json";
export default {
  data() {
    return {
      workHistoryAlls: [],
    };
  },
  async beforeMount() {
    this.workHistoryAlls = await data.workHistoryAlls;
  },
};
</script>

<style lang="scss" scoped>
#work_history {
  position: relative;
  .bg_my img {
    height: 160vh;
    object-fit: cover;
    @include responsive_md() {
      height: 220vh;
    }
    @include responsive_xxxs() {
      height: 250vh;
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