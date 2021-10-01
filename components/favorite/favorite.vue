<template>
  <!-- สกิลหลัก -->
  <section class="pa-4" id="favorite">
    <ul>
      <li
        class="elevation-5 rounded-lg pa-4"
        data-aos="fade-up"
        data-aos-duration="1500"
      >
        <figure><img src="@/assets/images/home/three-02.svg" alt="" /></figure>
        <div>
          <h2 class="font-weight-bold">Web Designer</h2>
          <p>I specialize in website design.</p>
        </div>
      </li>
      <li
        class="elevation-5 rounded-lg pa-4"
        data-aos="fade-up"
        data-aos-duration="2000"
      >
        <figure><img src="@/assets/images/home/three-03.svg" alt="" /></figure>
        <div>
          <h2 class="font-weight-bold">Photographer</h2>
          <p>I have the ability to take pictures and edit images.</p>
        </div>
      </li>
      <li
        class="elevation-5 rounded-lg pa-4"
        data-aos="fade-up"
        data-aos-duration="2500"
      >
        <figure><img src="@/assets/images/home/three-01.svg" alt="" /></figure>
        <div>
          <h2 class="font-weight-bold">Graphic Design</h2>
          <p>I have the ability to draw vector and design banners.</p>
        </div>
      </li>
    </ul>
  </section>
  <!-- end สกิลหลัก -->
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#favorite ul {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(30rem, 1fr));
  grid-gap: 1.6rem;
  @include responsive_xxs() {
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
  }
  li {
    @include flex_center_start();
    gap: 1.6rem;
    img {
      max-width: 8rem;
      width: 8rem;
      @include responsive_xxs() {
        max-width: 5rem;
        width: 5rem;
      }
    }
  }
}
</style>