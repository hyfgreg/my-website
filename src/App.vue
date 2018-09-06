<template>
  <v-app>
    <navigation-list :items="items" :drawer="drawer" :miniVariant="miniVariant"></navigation-list>
    <v-toolbar app
               :clipped-left="true">
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-avatar><img src="@/assets/ourlogo.png"></v-avatar>
      <v-btn icon
             @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer app fixed>
      <v-layout justify-center
                row
                wrap>
        <span>&copy; 2018</span>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
import menu from '@/menu'
import NavigationList from '@/components/NavigationList'

export default {
  components: {
    NavigationList
  },
  data () {
    return {
      drawer: true,
      items: menu,
      miniVariant: false,
      title: 'Vuetify.js'
    }
  },
  name: 'App'
}
</script>
