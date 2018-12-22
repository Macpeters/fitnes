<template>
  <section class="links">
    <span><nuxt-link to="/">Home</nuxt-link></span>
    <span><nuxt-link to="/heartrate">Heartrate</nuxt-link></span>
    <span><nuxt-link to="/userProfile">Profile</nuxt-link></span>
  </section>
</template>

<script>
export default {
  components: {
  }
}
</script>

<style scoped>

.links {
  display: block;
  background-color: #ccc;
  width: 100%;
  padding-top: 15px;
}
span {
  padding: 10px;
  font-weight: 600;
}

a {
  text-decoration: none;
}
</style>
