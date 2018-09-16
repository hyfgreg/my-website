<template>
  <v-app>
    <v-toolbar app>
      <router-link tag="a" to="/"><img src="@/assets/ourlogo.png" class="custom-avatar"></router-link>
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-toolbar>
    <section style="margin-top:63px">
      <router-view/>
    </section>
  </v-app>
</template>

<script>
import menu from '@/menu'

export default {
  components: {
  },
  data () {
    return {
      items: menu,
      title: '张肉排'
    }
  },
  name: 'App'
}
</script>

<style>
.custom-avatar{
  height: 48px;
  display: block;
}
</style>

