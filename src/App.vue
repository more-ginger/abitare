<template>
  <div id="app" ref="container">
    <Home />
    <Esse5 :width="width" :height="height" />
  </div>
</template>

<script>
import Home from './components/Home.vue'
import Esse5 from './components/S5.vue'

export default {
  name: 'App',
  components: {
    Home,
    Esse5
  },
  data () {
    return {
      width: 0,
      height: 0
    }
  },
  methods: {
    calcSizes () {
      const { container: el } = this.$refs
      const totalWidth = el.clientWidth
      const totalHeight = el.clientHeight || el.parentNode.clientHeight
      this.width = Math.max(totalWidth, 500)
      this.height = Math.max(totalHeight, 500)
    }
  },
  mounted () {
    this.calcSizes()
    window.addEventListener('resize', this.calcSizes, false)
  },
  updated () {
    this.calcSizes()
  },
  beforeDestroy () {
    window.removeEventListener('resize', this.calcSizes, false)
  }
}
</script>

<style lang="scss">
@import "./style/global.scss";

#app {
  margin: 0 auto;
  height: 100vh;

  h1 {
    padding-top: 25%;
    font-size: 120px;
    height: 120px;
  }

  h1, h2, h3 {
    font-family: $staatliches;
    color: $blue;
  }

  h3 {
    margin-top: 40px;
  }

  p {
    margin-top: 30px;
    font-family: $karla;
    color: #2c3e50;
    margin: 0 auto;
  }

  #data {
    color: $red;
  }
}
</style>
