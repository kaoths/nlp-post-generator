<template>
  <v-app>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color='secondary'
    >
      <div class="d-flex flex-1"></div>
      <div class='d-flex flex-1 justify-center text-white'>
        <v-toolbar-title v-text="title" />
      </div>
      <div class="d-flex flex-1 justify-end align-center">
        <v-switch
          dark
          inset
          color='white'
          :style="{ marginTop: '20px' }"
          v-model="$vuetify.theme.dark"
          prepend-icon="mdi-theme-light-dark"
        ></v-switch>
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
      color='secondary'
    >
      <div class="w-100 d-flex justify-center text-white">
        <span>CeleBERTy &copy; {{ new Date().getFullYear() }}</span>
      </div>
    </v-footer>
  </v-app>
</template>

<script lang='ts'>
import { Vue, Component } from 'nuxt-property-decorator'
@Component
export default class DefaultLayout extends Vue {
  private clipped = false
  private fixed = false
  private title = "NLP Pantip's post generation"
}
</script>

<style scoped>
.w-100 {
  width: 100%
}
.flex-1 {
  flex: 1;
}
.text-white {
  color: white !important;
}
</style>
