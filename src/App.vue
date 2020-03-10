<template>
  <div id="app" ref="container">
    <h1 class="pagetitle">Abitare il Limite</h1>
    <p id="data">29.02.2020</p>
    <h3>S5 Westkreuz  ⇌ Ostbanhof</h3>
    <p>Abbiamo percorso la linea S5 da Ostbanhof a Westkreuz.</p>
    <Esse5 :width="width" :height="height" />
  </div>
</template>

<script>
import Esse5 from './components/S5.vue'

export default {
  name: 'App',
  components: {
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
  max-width: 900px;
  margin: 0 auto;

  height: 100vh;

  h1 {
    padding-top: 200px;
  }

  h1, h3 {
    font-family: $libre;
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

  .pagetitle {
    padding-bottom: 20px;
    border-bottom: 1px solid $red;
  }

  #data {
    color: $red;
  }
}
</style>
