<template>
  <div>
    <section class="calc bg_disabled" id="curriculum_vitae">
      <v-container>
        <v-row>
          <v-col cols="12" class="bg_secondary">
            <section class="grid_vitae py-4">
              <div class="left_vitae">
                <div class="mb-8">
                  <div class="mb-4">
                    <h2
                      class="font-weight-bold color_line font_head mb-2"
                      style="line-height: 1"
                    >
                      Chatthong Hongwisuthikul
                    </h2>
                    <h3 class="color_primary">Web Designer</h3>
                  </div>
                  <!-- รูป โปรไฟล์ -->
                  <div class="text-center">
                    <figure class="cv_pic mb-4">
                      <img
                        src="@/assets/images/curriculumVitae/vitae.jpg"
                        alt=""
                      />
                    </figure>
                  </div>
                  <!-- end รูป โปรไฟล์ -->
                </div>

                <article>
                  <!-- วัน เดือน ปี เกิด -->
                  <div class="flex_cv mb-4">
                    <figure class="cv_icon bg_info">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-01.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>
                        <span class="font-weight-bold">Birthday :</span> 30
                        January 1987
                      </p>
                      <p>
                        <span class="font-weight-bold">Age :</span>
                        {{ ages }} years old
                      </p>
                      <p>
                        <span class="font-weight-bold">Height :</span> 165 cm.
                      </p>
                      <p>
                        <span class="font-weight-bold">Weight :</span> 55 kg.
                      </p>
                      <p><span class="font-weight-bold">Sex :</span> Male</p>
                      <p>
                        <span class="font-weight-bold">Status :</span> Single
                      </p>
                      <p>
                        <span class="font-weight-bold">Nationality</span> : Thai
                      </p>
                      <p>
                        <span class="font-weight-bold">Religion</span> : Buddha
                      </p>
                    </div>
                  </div>
                  <!-- end วัน เดือน ปี เกิด -->

                  <hr class="dashed my-4" />

                  <!-- ที่อยู่ -->
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon bg_warning">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-02.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>
                        447 Lat Phrao 109 Road, Khlong Chan Subdistrict, Bang
                        Kapi District, Bangkok 10240
                      </p>
                    </div>
                  </div>
                  <!-- end ที่อยู่ -->

                  <hr class="dashed my-4" />

                  <!-- เมล -->
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon bg_error">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-03.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>dynastystrike@gmail.com</p>
                    </div>
                  </div>
                  <!-- end เมล -->

                  <hr class="dashed mb-4" />

                  <!-- เฟสบุ๊ค -->
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon width">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-04.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>chatthong hongwisuthikul</p>
                    </div>
                  </div>
                  <!-- end เฟสบุ๊ค -->

                  <hr class="dashed my-4" />
                  <!-- ไลน์ -->
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon" style="background: #07b53b">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-05.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>chat_skysword</p>
                    </div>
                  </div>
                  <!-- end ไลน์ -->

                  <hr class="dashed my-4" />

                  <!-- มือถือ -->
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon bg_link">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-06.svg"
                        alt=""
                      />
                    </figure>
                    <div>
                      <p>08-9762-0645</p>
                    </div>
                  </div>
                  <!-- end มือถือ -->

                  <hr class="dashed my-4" />

                  <!-- ทักษะ -->
                  <div>
                    <div class="flex_cv center_cv mb-4">
                      <figure class="cv_icon bg_success">
                        <img
                          src="@/assets/images/curriculumVitae/CurriculumVitae-07.svg"
                          alt=""
                        />
                      </figure>
                      <div>
                        <p>Skill</p>
                      </div>
                    </div>

                    <article>
                      <div class="bg_disabled rounded-lg pa-4">
                        <section
                          class="flex_vitae_skill"
                          v-for="curricurlumVitae in curricurlumVitaes"
                          :key="curricurlumVitae.id"
                        >
                          <figure>
                            <img
                              :src="
                                require(`@/assets/images/curriculumVitae/${curricurlumVitae.icon}`)
                              "
                              :alt="curricurlumVitae.name"
                            />
                          </figure>

                          <div>
                            <p>{{ curricurlumVitae.name }}</p>
                            <!-- หากเปอเซน มากกว่า 50 -->
                            <div v-if="curricurlumVitae.skill >= 50">
                              <v-progress-linear
                                color="red darken-2"
                                v-model="curricurlumVitae.skill"
                                height="20"
                                :rounded="true"
                                reactive
                                class="mb-4"
                              >
                                <template v-slot="{ value }">
                                  <span class="color_secondary"
                                    >{{ Math.ceil(value) }}%</span
                                  >
                                </template>
                              </v-progress-linear>
                            </div>
                            <!-- end หากเปอเซน มากกว่า 50 -->

                            <!-- หากเปอเซน น้อยกว่า 50 -->
                            <div v-else>
                              <v-progress-linear
                                color="red darken-2"
                                v-model="curricurlumVitae.skill"
                                height="20"
                                :rounded="true"
                                reactive
                                class="mb-4"
                              >
                                <template v-slot="{ value }">
                                  <span class="color_text"
                                    >{{ Math.ceil(value) }}%</span
                                  >
                                </template>
                              </v-progress-linear>
                            </div>
                            <!-- end หากเปอเซน น้อยกว่า 50 -->
                          </div>
                        </section>
                      </div>
                    </article>
                  </div>
                  <!-- end ทักษะ -->
                </article>
              </div>

              <div class="right_vitae">
                <section>
                  <div class="flex_cv center_cv mb-4">
                    <figure class="cv_icon bg_info">
                      <img
                        src="@/assets/images/curriculumVitae/CurriculumVitae-17.svg"
                        alt=""
                      />
                    </figure>
                    <h2>Education</h2>
                  </div>

                  <div>
                    <p>
                      <span class="font-weight-bold">มหาวิทยาลัย : </span
                      >ราชภัฎสวนสุนันทา (2004 - 2008)
                    </p>
                    <p>
                      <span class="font-weight-bold">ระดับการศึกษา : </span
                      >ปริญญาตรี
                    </p>
                    <p>
                      <span class="font-weight-bold">สาชาวิชา : </span
                      >ออกแบบนิเทศศิลป์
                    </p>
                    <p><span class="font-weight-bold">GPA : </span>3.07</p>
                  </div>
                </section>

                <hr class="dashed my-4" />

                <div class="flex_cv center_cv mb-4">
                  <figure class="cv_icon bg_error">
                    <img
                      src="@/assets/images/curriculumVitae/CurriculumVitae-18.svg"
                      alt=""
                    />
                  </figure>
                  <h2>Work History</h2>
                </div>

                <div>
                  <div
                    v-for="workHistory in workHistorys"
                    :key="workHistory.id"
                    class="grid_work_cv"
                  >
                    <p>{{ workHistory.id }}</p>
                    <div>
                      <p>
                        <b>Company :</b>
                        <span class="color_primary">{{
                          workHistory.company
                        }}</span>
                      </p>
                      <p><b>Duration :</b> {{ workHistory.date }}</p>
                      <p><b>Position :</b> {{ workHistory.position }}</p>
                      <p><b>Salary :</b> {{ workHistory.salary }}</p>
                      <p><b>Responsibility :</b> {{ workHistory.detail }}</p>
                    </div>
                    <hr class="dashed mb-4 grid_span" />
                  </div>
                </div>
              </div>
            </section>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
import data from "@/data/data.json";
export default {
  data() {
    return {
      curricurlumVitaes: [],
      workHistorys: [],
      ages: "",
    };
  },
  async beforeMount() {
    this.curricurlumVitaes = await data.curricurlumVitaes;
    this.workHistorys = await data.workHistorys;
  },
  mounted() {
    let startYear = new Date("1987-01-30");
    let currentYear = new Date();
    this.ages = currentYear.getFullYear() - startYear.getFullYear();
  },
};
</script>

<style lang="scss" scpoed>
#curriculum_vitae {
  .grid_vitae {
    display: grid;
    grid-template-columns: 40rem 1fr;
    grid-gap: 3rem;
    @include responsive_md() {
      grid-template-columns: 1fr;
    }
    .left_vitae .cv_red {
      background: $color_primary;
      height: 4rem;
    }
    .left_vitae .flex_cv,
    .right_vitae .flex_cv {
      @include flex_start_start();
      &.center_cv {
        @include flex_center_start();
      }
      gap: 1.6rem;
      .cv_icon {
        @include flex_center_center();
        border-radius: 50%;
        flex-shrink: 0;
        padding: 0.8rem;
        &.width {
          padding: 0;
          img {
            max-width: 4.1rem;
            height: 4.1rem;
          }
        }
      }
      img {
        max-width: 2.5rem;
        height: 2.5rem;
      }
    }
    .left_vitae .flex_vitae_skill {
      @include flex_center_start();
      gap: 1.6rem;
      figure {
        flex-shrink: 0;
      }
      img {
        max-width: 4rem;
      }
      & > div {
        flex-basis: 100%;
      }
    }
    .right_vitae .grid_work_cv {
      display: grid;
      grid-template-columns: 1rem 1fr;
      grid-gap: 1.6rem;
      &:last-child hr {
        border: none !important;
      }
      .grid_span {
        grid-column: 1/3;
      }
    }
  }
}
</style>