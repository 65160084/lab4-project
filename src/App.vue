<script setup lang="ts">

import { ref } from 'vue'
import { mdiWeatherSunny, mdiWeatherNight, mdiAccountCheck, mdiFolder, mdiAccountMultiple, mdiStar } from '@mdi/js'
const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-app :theme="theme">
    <v-app-bar>
      <v-spacer></v-spacer>

      <v-btn :prepend-icon="mdiAccountCheck" color="blue">Button</v-btn>

      <v-btn :prepend-icon="theme === 'light' ? mdiWeatherSunny : mdiWeatherNight" @click="onClick">
        Toggle theme
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer expand-on-hover rail permanent>
      <v-list>
        <v-list-item
          prepend-avatar="https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F6%2F2013%2F05%2Fb31.jpg&q=60"
          title="Meme" subtitle="ABCDEF_-@gmail.com"></v-list-item>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item :prepend-icon="mdiFolder" title="My Files" value="myfiles" to="/my-flies-view"></v-list-item>

        <v-list-item :prepend-icon="mdiAccountMultiple" title="Shared with me" value="shared" to="/share-with-me"></v-list-item>

        <v-list-item :prepend-icon="mdiStar" title="Starred" value="starred" to="/starred"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<style></style>

