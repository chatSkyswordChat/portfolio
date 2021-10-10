<template>
  <section id="my_skill" class="py-4">
    <h2 class="font_head mb-4">My Skill</h2>
    <v-row>
      <v-col cols="12" md="6">
        <div
          v-for="(item, index) in items"
          :key="index.id"
          data-aos="fade-right"
          data-aos-duration="1500"
        >
          <p class="font_superText">{{ item.name }}</p>
          <v-progress-linear
            color="red darken-2"
            v-model="item.skill"
            height="20"
            :rounded="true"
            reactive
            class="mb-4"
          >
            <template v-slot="{ value }">
              <span class="color_secondary">{{ Math.ceil(value) }}%</span>
            </template>
          </v-progress-linear>
        </div>
      </v-col>

      <v-col cols="12" md="6">
        <section class="skill">
          <div v-for="(skill, index) in skills" :key="index">
            <v-hover v-slot:default="{ hover }">
              <div
                class="bg_ability elevation-5 rounded-lg"
                :data-aos="skill.fade"
                :data-aos-duration="skill.number"
              >
                <div class="ability pa-4">
                  <figure>
                    <img
                      :src="require(`@/assets/images/home/${skill.src}`)"
                      alt=""
                    />
                  </figure>
                  <h6 class="font_text text-center">{{ skill.name }}</h6>
                </div>
                <v-expand-transition>
                  <div
                    v-if="hover"
                    class="
                      d-flex
                      transition-fast-in-fast-out
                      v-card--reveal
                      white--text
                      bg_text
                      rounded-lg
                    "
                    style="height: 100%"
                  >
                    <span class="text-center pa-4">{{ skill.detail }}</span>
                  </div>
                </v-expand-transition>
              </div>
            </v-hover>
          </div>
        </section>
      </v-col>
    </v-row>
  </section>
</template>

<script>
import data from "@/data/data.json";
export default {
  data() {
    return {
      items: [],
      skills: [],
    };
  },
  async created() {
    this.items = await data.items;
    this.skills = await data.skills;
  },
};
</script>

<style lang="scss" scoped>
#my_skill {
  .skill {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(18rem, 1fr));
    grid-gap: 3rem;
    .bg_ability {
      position: relative;
      height: 100%;
      .ability {
        @include flex_center_center();
        flex-direction: column;
        position: relative;
        img {
          max-width: 15rem;
        }
      }
      .v-card--reveal {
        @include flex_center_center();
        bottom: 0;
        right: 0;
        opacity: 0.8;
        position: absolute;
        width: 100%;
      }
    }
  }
}
</style>