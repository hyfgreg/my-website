<template>
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
</template>

<script>
export default {
  name: 'NavigationList',
  props: ['items', 'drawer', 'miniVariant']
}
</script>

<style>
</style>
