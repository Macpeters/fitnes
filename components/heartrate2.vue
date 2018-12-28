<template>
  <section class="container">
    <h2>Draw the graph using coloured divs</h2>
    <div class="heartrates">
      <ul>
        <li class="item" v-for="(item, index) in day" :key="index">
          <div class="value" v-bind:style="{ height: 150 - item.value.bpm + 'px;' }" ><span class="item-value">{{item.value.bpm}}</span></div>
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
  background-color: rgb(212, 102, 102);
  width: 10px;
  display: inline-block;
  margin: 2px;
  /* opacity: 0; */
  z-index: 1;
}

.item:hover {
  width: 25px;
  /* opacity: 1; */
  color: white;
  background-color: red;
  font-weight: 800;
  z-index: 300;
}

.item-value {
  /* opacity: 0; */
}
.item-value:hover {
  color: white;
}

.value {
  background-color: black;
}

</style>
