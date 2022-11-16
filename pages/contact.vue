<template>
  <div>
    <section id="contact">
      <figure class="bg_contact">
        <picture>
          <source
            srcset="@/assets/images/contact/contact.webp"
            type="image/webp"
          />
          <source
            srcset="@/assets/images/contact/contact.jpg"
            type="image/jpg"
          />
          <img class="calc" src="@/assets/images/contact/contact.jpg" alt="" />
        </picture>
      </figure>

      <v-col cols="12" class="contact">
        <div class="inset_contact">
          <h1 class="mb-4 color_secondary">Contact</h1>
          <div class="mb-8">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3875.1101868660153!2d100.63413631465448!3d13.77222819033428!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x311d61f69cda26b9%3A0xe7335e9bf59d0a9a!2z4LiL4Lit4LiiIOC4peC4suC4lOC4nuC4o-C5ieC4suC4pyAxMDkg4LmB4LiC4Lin4LiHIOC4hOC4peC4reC4h-C4iOC4seC5iOC4mSDguYDguILguJXguJrguLLguIfguIHguLDguJvguLQg4LiB4Lij4Li44LiH4LmA4LiX4Lie4Lih4Lir4Liy4LiZ4LiE4LijIDEwMjQw!5e0!3m2!1sth!2sth!4v1594735658996!5m2!1sth!2sth"
              width="600"
              height="400"
              frameborder="0"
              style="border: 0"
              allowfullscreen=""
              aria-hidden="false"
              tabindex="0"
              class="map"
            ></iframe>
          </div>
          <div class="grid_contact mb-8">
            <figure
              v-for="item in items"
              :key="item.id"
              :data-aos="item.fade"
              :data-aos-duration="item.number"
              class="bg_secondary text-center rounded-lg elevation-5 pa-4"
            >
              <img :src="item.icon" alt="" />
              <p class="font_superText">{{ item.name }}</p>
            </figure>
          </div>
        </div>
      </v-col>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: "08-9762-0645",
          icon: require("@/assets/images/contact/app-01.svg"),
          fade: "fade-left",
          number: "500"
        },
        {
          name: "dynastystrike@gmail.com",
          icon: require("@/assets/images/contact/app-02.svg"),
          fade: "fade-down",
          number: "1000"
        },
        {
          name: "chatthong hongwisuthikul",
          icon: require("@/assets/images/contact/app-03.svg"),
          fade: "fade-right",
          number: "1500"
        },
        {
          name: "chat_skysword",
          icon: require("@/assets/images/contact/app-04.svg"),
          fade: "fade-up",
          number: "2000"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
#contact {
  max-width: 118.5rem;
  margin-inline: auto;
  position: relative;
  .bg_contact {
    position: absolute;
    width: 100%;
    height: 100%;
    img {
      height: 100%;
      object-fit: cover;
      position: absolute;
    }
  }
  .contact {
    position: relative;
    &::before {
      height: 100%;
      position: absolute;
      content: "";
      top: 0;
      left: 0;
      z-index: 1;
      background: rgba(0, 0, 0, 0.5);
      max-width: 100vw;
      width: 100vw;
      margin: 0 calc(-50vw + 50%);
    }
    .inset_contact {
      position: relative;
      z-index: 2;
      iframe {
        max-width: 117rem;
        width: 100%;
      }
    }
    .grid_contact {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(25rem, 1fr));
      grid-gap: 3rem;
      figure {
        @include flex_center_center();
        flex-direction: column;
        gap: 1.6rem;
        img {
          max-width: 10rem;
        }
      }
    }
  }
}
</style>
