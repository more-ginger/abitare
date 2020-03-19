<template>
  <div class="hello">
    <div class="hello-internal">
      <h3>Westkreuz ↔︎ Ostbanhof</h3>
      <p id="data">29.02.2020</p>
      <p>La S5 attraversa la città per il lungo: da Westkreuz (situata a ovest)
      della città, fino a Strausberg a circa 30km da Berlino.<br />
      </p>
      <img src="../assets/svg/s5_first.svg"/>
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
    background-color: white;

    width: 100%;
  }

  .hello-internal {
    max-width: 900px;
    margin: 0 auto;
    padding-top: 100px;

    img {
      width: 100%;
    }

    .photos {
      margin-top: 100px;

    }

    .photo {
      padding-right: 10px;
      width: 15%;
      display: inline-flex;
      align-content: flex-start;
    }
  }
</style>
