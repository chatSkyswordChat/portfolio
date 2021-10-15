<template>
  <!-- แนะนำตัว -->
  <section id="present">
    <figure class="bg_my">
      <picture>
        <source srcset="@/assets/images/home/bg1.webp" type="image/webp" />
        <source srcset="@/assets/images/home/bg1.jpg" type="image/jpg" />
        <img class="calc" src="@/assets/images/home/bg1.jpg" alt="" />
      </picture>
    </figure>

    <div class="bg_myName">
      <div
        class="my_name pa-4 rounded-lg elevation-5 text-center"
        data-aos="fade-up"
        data-aos-duration="2000"
      >
        <h1>I'm Chatthong Hongwisuthikul</h1>
        <h2>Web Designer</h2>
        <h3>
          Have experience in
          <span :style="styleYears">{{ years }}</span> years old web designer,
          print design and photography and image decoration
        </h3>

        <hr class="dashed ma-4" />

        <ul class="contact">
          <li>
            <font-awesome-icon
              class="font_head color_primary"
              :icon="['fas', 'envelope']"
            />
            <p>dynastystrike@gmail.com</p>
          </li>
          <li>
            <a
              href="https://www.facebook.com/chatthong.hongwisuthikul"
              target="_blank"
              class="color_text"
            >
              <font-awesome-icon
                class="font_head"
                style="color: #1877f2"
                :icon="['fab', 'facebook']"
              />
              <p>chatthong hongwisuthikul</p>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </section>
  <!-- end แนะนำตัว -->
</template>

<script>
export default {
  data() {
    return {
      years: "",
      styleYears: {
        color: "#d40101",
        fontWeight: "bold",
      },
    };
  },
  mounted() {
    let startYear = new Date("2011-01-01");
    let currentYear = new Date();
    this.years = currentYear.getFullYear() - startYear.getFullYear();
  },
};
</script>

<style lang="scss" scoped>
#present {
  position: relative;
  .bg_my img {
    height: 100vh;
    object-fit: cover;
  }
  .bg_myName {
    position: absolute;
    top: 50%;
    right: 0;
    transform: translate(0, -50%);
    max-width: 57.6rem;
    width: 100%;
    @include responsive_md() {
      left: 50%;
      transform: translate(-50%, -50%);
    }
    .my_name {
      background: rgba(255, 255, 255, 0.7);
      h1 {
        font-size: clamp(3rem, 2.5vw, 6rem);
      }
      h2 {
        font-size: clamp(6rem, 2.5vw, 10rem);
        font-weight: bold;
        color: $color_primary;
      }
      h3 {
        font-size: $font_subHead;
      }
      .contact {
        @include flex_center_center();
        gap: 3.2rem;
        flex-wrap: wrap;
      }
    }
  }
}
</style>