<template>
  <div>
    <v-parallax :src="require('@/assets/lover.jpg')" height="550">
      <v-layout column align-center justify-center class="white--text">
        <img :src="require('@/assets/ourlogo.png')" alt="Vuetify.js" height="200">
        <h1 class="white--text mb-2 display-1 text-xs-center">{{ sayHi }}</h1>
        <v-btn class="pink lighten-2 mt-5" dark large @click="$vuetify.goTo('#main-content')">
          开始旅程 &nbsp;
          <v-icon>thumb_up</v-icon>
        </v-btn>
      </v-layout>
    </v-parallax>
    <v-container grid-list-xl ma-auto>
      <v-layout wrap>
        <v-flex xs12 text-xs-center>
          <h1 id="main-content" class="display-1 text-xs-center">看看新鲜事</h1>
        </v-flex>
        <v-flex xs12>
          <v-layout wrap justify-space-around>
            <template v-for="(item,index) in article">
              <v-flex :key="item.name" xs12 sm4 md4>
                <v-card @click.native="goto(item.to)" style="cursor: pointer" flat @mouseover="mouseOnWhich(index)" @mouseout="mouseOutWhich(index)" :class="{'elevation-10':isMouseOver[index]}">
                  <v-img :src="item.src" aspect-ratio="1"></v-img>
                  <v-card-title style="padding-bottom:0" class="justify-center">
                    <h1 class="headline">{{ item.name }}</h1>
                  </v-card-title>
                  <v-card-text>
                    {{ item.description }}
                  </v-card-text>
                </v-card>
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>
    <v-parallax :src="require('@/assets/parallax.jpeg')" height="400">
    </v-parallax>
    <rooter-component></rooter-component>
  </div>
</template>

<script>
import RooterComponent from '../components/RooterComponent'
export default {
  components: {RooterComponent},
  data () {
    return {
      isMouseOver: [],
      article: [
        {
          name: '今天天气不错',
          description: '啦啦啦',
          src: 'https://picsum.photos/500/300?image=0',
          to: {name: 'test'}
        },
        {
          name: '今天饭好吃',
          description: '哈哈哈',
          src: 'https://picsum.photos/500/300?image=15',
          to: {name: 'HelloWorld'}
        },
        {
          name: '今天喝啤酒',
          description: '哟哟哟',
          src: 'https://picsum.photos/500/300?image=10',
          to: {name: 'HelloWorld'}
        }
      ],
      greeting: [
        '这个点是不是该去睡觉~',
        '早上好呀~',
        '中午好呀~',
        '下午好呀~',
        '晚上好呀~'
      ]
    }
  },
  methods: {
    goto (value) {
      this.$router.push(value)
    },
    getNowHour () {
      let date = new Date()
      // console.log(date)
      let hour = date.getHours()
      return hour
    },
    mouseOnWhich (index) {
      this.$set(this.isMouseOver, index, true)
    },
    mouseOutWhich (index) {
      this.$set(this.isMouseOver, index, false)
    }
  },
  computed: {
    // articleNum () {
    //   return this.article.length
    // },
    sayHi () {
      let hour = this.getNowHour()
      if (hour >= 6 && hour < 11) {
        return this.greeting[1]
      } else if (hour >= 11 && hour < 13) {
        return this.greeting[2]
      } else if (hour >= 13 && hour < 18) {
        return this.greeting[3]
      } else if (hour >= 18 && hour < 23) {
        return this.greeting[4]
      } else {
        return this.greeting[0]
      }
    }
  },
  mounted () {
    let articleNum = this.article.length
    // this.isMouseOver = []
    for (let i = 0; i < articleNum; i++) {
      this.isMouseOver.push(false)
    }
  }
}
</script>

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
