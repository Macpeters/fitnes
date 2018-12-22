<template>
  <section class="container">
    <div>
      <h1 class="title">
        Heart Rate
      </h1>

      <div class="heartrates">
        <ul>
          
          <li class="item" v-for="(item, index) in Dec03" :key="index">
            <span class="bar" v-bind:style="{ top: 150 - item.value.bpm + 'px' }" v-bind:title="item.value.bpm">
              *<img class="heartrate-line" src="~/assets/blueLine.svg">
            </span>
            <span class="foo">*</span>
          </li>
        </ul>  
      </div>

      <div class="imagetest">
        IMAGE TEST
         <img class="blue-line" src="~/assets/blueLine.svg">
      </div>

      <hr/>
      <h2 class="subtitle">
        {{Dec03}}
      </h2>
    </div>
  </section>
</template>

<script>
  export default {
    async asyncData({ app, params, error }) {
      let Dec03 = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/heart_rate-2018-12-03.json')
      return { Dec03 }
    }
  }
</script>

<style scoped>
  .container {
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

  .imagetest {
    background-color:#ddd;
  }

  .blue-line {
    position: relative;
    padding-top: 5px;
    height: 100px;
    transform: rotate(10deg);
  }

  .heartrates {
    overflow: hidden;
    width: 100%;
    height: 150px;
  }

  ul {
    white-space: nowrap;
    overflow: hidden;
    overflow-x:scroll;
  }

  li {
    display: inline-block;
    list-style: none;
    position: relative;
    height: 150px;
    width: 10px;
  }

  img {
    opacity: 0.5;
  }

 
  .bar {
    position: relative;
  }
/* 
  .bar img:nth-child(2n) {
    transform: rotate(10deg);
    opacity: 0.5;

  }

  .bar img:nth-child(2n + 1) {
    transform: rotate(170deg);
  }
 */

   .foo {
    top: 140px;;
    position: relative;
  }

</style>
