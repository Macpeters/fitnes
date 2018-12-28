<template>
  <section class="container">
    <h2>Create a slider of Divs</h2>
    <div class="heartrates">
      <ul>
        <li class="item" v-for="(item, index) in day" :key="index">
          <div class="value" v-bind:style="{ opacity: (item.value.bpm-50)/100 }" >
            <div class="spacer"></div>
            <span class="item-value">{{item.value.bpm}}</span>
          </div>
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
    color: black;
    background-color: black;
    overflow: hidden;
  }

  ul {
    white-space: nowrap;
    overflow: hidden;
    overflow-x:scroll;
  }

  li {
    display: inline-block;
  }

  .spacer {
    height: 40px;
    width: 100px;
    /* background-color: red; */
  }

  .value {
    height: 100px;
    width: 100px;
    background-color: blue;
    margin: 5px;
    display: inline-block;
    text-align: center;
    font-weight: bolder;
    cursor:-webkit-grab;
  }

  .value:hover {
    /* font-size: 24px; */
  }

  .item-value {
    padding-top: 30%;
    color: white;
  }
</style>
