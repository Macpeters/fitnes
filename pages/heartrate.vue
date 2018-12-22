<template>
  <section class="container">
    <div>
      <h1 class="title">
        Heart Rate
      </h1>
      <h2 class="subtitle">
        show something here
      </h2>
    </div>
  </section>
</template>

<script>
// import navbar from '~/components/navbar.vue'

export default {
  components: {
    // navbar
  }
}
</script>

<style scoped>

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

</style>
