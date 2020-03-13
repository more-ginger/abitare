<template>
  <div class="hello">
    <img src="../assets/svg/s5_first.svg"/>
    <p>ciao!</p>
    <div class="photos">
      <img
      v-for="(photo, i) in photos"
      v-bind:key="i"
      class="photo"
      :src="getImgUrl(photo.link)"
      v-bind:alt="photo.number"
      />
    </div>
  </div>
</template>

<script>
import photos from '../assets/photos.json'

export default {
  name: 'Esse5',
  props: {
    height: Number,
    width: Number
  },
  data () {
    return {
      photos
    }
  },
  methods: {
    getImgUrl (photo) {
      return require('../assets/data/' + photo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .hello {
    margin-top: 100px;

    width: 100%;
    height: 100%;

    img {
      width: 100%;
    }

    .photos {
      margin-top: 100px;

    }

    .photo {
      padding-right: 5px;
      width: 20%;
      display: inline-grid;
    }

  }
</style>
