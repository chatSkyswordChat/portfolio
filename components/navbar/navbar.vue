<template>
  <div>
    <v-app-bar tile fixed color="white" class="navbar">
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = true"
      ></v-app-bar-nav-icon>

      <v-spacer class="hidden-md-and-up"></v-spacer>

      <v-toolbar-title class="logo">
        <nuxt-link to="/">
          <img src="@/assets/images/home/logoChatSkysword.svg" alt="" />
        </nuxt-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn
        v-for="(menu, index) in menus"
        :key="index.id"
        text
        exact-active-class="active"
        :to="menu.route"
        class="btn_menu hidden-sm-and-down"
      >
        {{ menu.name }}
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed temporary>
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item
            v-for="(menu, index) in menus"
            :key="index.id"
            :to="menu.route"
            class="btn_menu"
            exact-active-class="active"
          >
            <v-list-item-icon class="icon mr-2">
              <font-awesome-icon
                class="font_superText"
                :icon="[menu.sign, menu.icon]"
              />
            </v-list-item-icon>
            <v-list-item-title class="mobile_menu">{{
              menu.name
            }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menus: [
        {
          name: "HOME",
          route: { name: "index" },
          sign: "fas",
          icon: "home",
        },
        {
          name: "Curriculum Vitae",
          route: { name: "curriculumVitae" },
          sign: "fas",
          icon: "portrait",
        },
        {
          name: "PORTFOLIO",
          route: { name: "portfolio" },
          sign: "fas",
          icon: "file",
        },
        {
          name: "WORK HISTORY",
          route: { name: "workHistory" },
          sign: "fas",
          icon: "graduation-cap",
        },
        {
          name: "CONTACT",
          route: { name: "contact" },
          sign: "fas",
          icon: "mobile-alt",
        },
      ],
      drawer: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  .logo a {
    @include flex_center();
    img {
      max-width: 10rem;
    }
  }
  .btn_menu {
    font-size: $font_text !important;
    transition: 0.5s ease-in-out;
    margin-right: 1.5rem;
    &.active,
    &:hover {
      background: $color_primary;
      color: $color_secondary;
    }
    &:last-child {
      margin-right: 0;
    }
  }
}

// ปุ่มเมนู mobile vuetify
.v-list-item--link {
  .icon {
    @include flex_center_center();
  }
  &::before {
    background-color: inherit !important;
  }
  .mobile_menu {
    font-size: $font_text;
    line-height: inherit;
  }
  &.active,
  &:hover {
    background: $color_primary;
    color: $color_secondary !important;
  }
}
// end ปุ่มเมนู mobile vuetify
</style>
