<template>
  <v-container fluid>
    <!-- <v-parallax src="@/assets/plane.png" dark></v-parallax> -->
    <section>
      <v-parallax :src="require('@/assets/parallax.jpeg')" height="600">
        <v-layout column align-center justify-center class="white--text">
          <img src="@/assets/ourlogo.png" alt="Vuetify.js" height="200">
          <h1 class="white--text mb-2 display-1 text-xs-center">晚上好呀~</h1>
          <v-btn class="blue lighten-2 mt-5" dark large @click="$vuetify.goTo('#main-content')">
            开始旅程
          </v-btn>
        </v-layout>
      </v-parallax>
    </section>
    <section>
      <v-layout column align-center id="main-content">
        <img src="@/assets/logo.png" alt="Vuetify.js" class="mb-5">
        <blockquote>
          &#8220;First, solve the problem. Then, write the code.&#8221;
          <footer>
            <small>
              <em>&mdash;John Johnson</em>
            </small>
          </footer>
        </blockquote>
      </v-layout>
    </section>
  </v-container>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
