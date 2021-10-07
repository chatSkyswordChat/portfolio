<template>
  <v-app>
    <navbar />

    <main>
      <v-container>
        <v-row>
          <v-col cols="12">
            <nuxt id="all" />
          </v-col>
        </v-row>
      </v-container>
    </main>
  </v-app>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#all {
  padding-top: 5.2rem;
  @include responsive_md() {
    padding-top: 4rem !important;
  }
}
</style>