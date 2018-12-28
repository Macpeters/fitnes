<template>
  <section class="container">
    <div>
      <h1 class="title">
        Heart Rate
      </h1>

      <div class="component">
        <heartrate2 :day="sliced"/>
      </div>

      <div class="component">
        <heartrate3 :day="sliced"/>
      </div>

      <div class="component">
        <heartrateScroller :day="sliced"/>
      </div>



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
  import heartrate3 from '~/components/heartrate3.vue'

  export default {
    components: {
      heartrateScroller: heartrateScroller,
      heartrate2: heartrate2,
      heartrate3: heartrate3
    },
    async asyncData({ app, params, error }) {
      let Dec03 = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/heart_rate-2018-12-03.json')
    //  we're just messing around with the first bit of data
     let sliced = Dec03.slice(0, 100);
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

  .component {
    margin-top: 30px;
  }

  .subtitle {
    margin-top: 100px;
  }
</style>
