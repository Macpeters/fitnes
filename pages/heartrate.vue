<template>
  <section class="container">
    <div>
      <h1 class="title">
        Heart Rate
      </h1>
      <heartrateScroller :day="sliced"/>
      <heartrate2 :day="sliced"/>
    

      <hr/>
      <h5 class="subtitle">
        <ul>
          <li v-for="(item, index) in sliced" :key="index">
            {{item}}
          </li>
        </ul>
      </h5>
    </div>
  </section>
</template>

<script>
  import heartrateScroller from '~/components/heartrateScroller.vue'
  import heartrate2 from '~/components/heartrate2.vue'
  export default {
    components: {
      heartrateScroller: heartrateScroller,
      heartrate2: heartrate2
    },
    async asyncData({ app, params, error }) {
      let Dec03 = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/heart_rate-2018-12-03.json')
    //  we're just messing around with the first bit of data
     let sliced = Dec03.slice(0, 200);
      return { sliced }
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
