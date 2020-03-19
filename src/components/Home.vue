<template>
  <div class="hello">
    <div class="head">
      <h1 class="pagetitle">Abitare il Limite</h1>
      <h2 class="subtitle">Diario di Progetto</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/global.scss";

.hello {
  // background-image: linear-gradient(270deg, $violet50, white);
  height: 100%;

}

.head {
  max-width: 800px;
  width: 90%;
  margin: 0 auto;
}

.pagetitle {
  text-align: center;
  margin-bottom: 0px;
}

.subtitle {
  margin-left: 31px;
  margin-top: 0px;
}

</style>
