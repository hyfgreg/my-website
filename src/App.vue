<template>
  <v-app>
    <v-navigation-drawer persistent
                         :mini-variant="miniVariant"
                         :clipped="true"
                         v-model="drawer"
                         enable-resize-watcher
                         fixed
                         app>
      <v-list>
        <template v-for="(item, i) in items">
          <v-list-tile :to="item.to"
                       :key="item.title">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app
               :clipped-left="true">
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-avatar><img src="@/assets/plane.png"></v-avatar>
      <v-btn icon
             @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer app>
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

export default {
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
