<template>
  <div>
     <navbar/>
    <nuxt/>
  </div>
</template>

<script>
  import navbar from '~/components/navbar.vue'
  export default {
    components: {
      navbar
    }
  }
</script>

<style>
  html {
    font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
    margin: 0;
  }

  .page-enter-active, .page-leave-active {
    transition: all .25s ease-out;
  }
  .page-enter, .page-leave-active {
    opacity: 0;
    transform-origin: 50% 50%;
  }

  .page-enter-active {
    animation: acrossIn .45s ease-out both;
  } 

  .page-leave-active {
    animation: acrossOut .65s ease-in both;
  } 

  @keyframes acrossIn {
    0% {
      transform: translate3d(-100%, 0, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }

  @keyframes acrossOut {
    0% {
      transform: translate3d(0, 0, 0);
    }
    100% {
      transform: translate3d(100%, 0, 0);
    }
  }

  .info:before {
    content: "";
    display: block;
    background: url("~assets/construction.png") no-repeat;
    width: 60px; 
    height: 60px; 
    float: left;
    margin: 0 6px 0 0;
  }
  .info {
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-weight: 700;
    padding: 20px;
  }
</style>
