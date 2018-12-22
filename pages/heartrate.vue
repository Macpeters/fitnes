<template>
  <section class="container">
    <div>
      <h1 class="title">
        Heart Rate
      </h1>
      <heartrates :day="Dec03"/>

    

      <hr/>
      <h5 class="subtitle">
        <ul>
          <li v-for="(item, index) in Dec03" :key="index">
            {{item}}
          </li>
        </ul>
      </h5>
    </div>
  </section>
</template>

<script>
  import heartrates from '~/components/heartrates.vue'
  export default {
    components: {
      heartrates: heartrates
    },
    async asyncData({ app, params, error }) {
      let Dec03 = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/heart_rate-2018-12-03.json')
      return { Dec03 }
    }
  }
</script>

<style scoped>
  .title {
    justify-content: center;
    align-items: center;
    text-align: center;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }
</style>
