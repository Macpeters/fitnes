<template>
  <section class="container">
    <div class="heartrates">
      <ul>
        <li class="item" v-for="(item, index) in day" :key="index">
          <span class="bar" v-bind:style="{ top: 150 - item.value.bpm + 'px' }" v-bind:title="item.value.bpm">
            <img class="heartrate-line" src="~/assets/blueLine.svg">
          </span>
          <span class="foo">*</span>
        </li>
      </ul>   
    </div>
  </section>
</template>

<script>
  export default {
    props: [
      'day'
    ]
  }
</script>

<style scoped>
  .heartrates {
    overflow: hidden;
    height: 150px;
  }

  ul {
    white-space: nowrap;
    overflow: hidden;
    overflow-x:scroll;
  }

  li {
    opacity: 0.5;
    display: inline-block;
    list-style: none;
    position: relative;
    width: 15px;
  }

  li:hover {
    opacity: 1;
  }

  img {
    /* margin-left: -100px; */
    opacity: 0.5;
  }

 
  .bar {
    position: relative;
    width: 10px;
  }

   .foo {
    top: 140px;;
    position: relative;
  }
</style>
