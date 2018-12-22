<template>
  <section class="container">
    <h2>Draw the graph using coloured divs</h2>
    <div class="heartrates">
      <ul>
        <li class="item" v-for="(item, index) in day" :key="index">
          <div class="value" v-bind:style="{ height: 150 - item.value.bpm + 'px;' }" >{{item.value.bpm}}</div>
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

.item {
  height: 150px;
  background-color: red;
  width: 10px;
  display: inline-block;
  margin: 2px;
  opacity: 0.5;
  z-index: 1;
}

.item:hover {
  width: 25px;
  opacity: 1;
  color: white;
  font-weight: 800;
  z-index: 300;
}

.value {
  background-color: black;
}

</style>
