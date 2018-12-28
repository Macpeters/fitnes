<template>
  <section class="container">
    <div>
      <div class="basic-info">
        <div><h1 class="title">{{profile.displayName}}</h1></div>
        <div>Age: {{profile.age}}</div>
        <div>Height: {{profile.height}}</div>
        <div>Country: {{profile.country}}</div>
        <div>DOB: {{profile.dateOfBirth}}</div>
      </div>

      <div class="info">
        <p>This page uses its own page transition - a fade in.</p>
        <p>The badges listed have a transitional hover effect.</p>
        <p>Clicking the badge will show a transitional background
          color, as defined by the json data.</p>
      </div>

      <div class="badges">
        <li class='list-badge' v-for="(badge, index) in profile.topBadges" :key="index">
          <div @click='choose(badge)'>
            <h3>{{badge.category}}</h3>
            <img v-bind:src="badge.image50px">
            <div>{{badge.shortDescription}}</div>
          </div>
        </li>
      </div>

      <div class="badge-details" v-bind:style="{ 'background-color': '#' + chosenBadge.badgeGradientEndColor }" >
        <h1>{{chosenBadge.shortName}}</h1>
        <h2>{{chosenBadge.description}}</h2>
        <h3>{{chosenBadge.mobileDescription}}</h3>
        <img v-bind:src="chosenBadge.image300px">
      </div>

    </div>
  </section>
</template>

<script>
  export default {
    transition: 'fadeOpacity',
    async asyncData({ app, params, error }) {
      let profile = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/userProfile.json')
      return { profile }
    },
    data() {
    return {
      chosenBadge: { }
    };
    },
    methods: {
    choose(badge) {
      this.chosenBadge = badge;
    }
  },
  }
</script>

<style>
  /* page transitions */
  .fadeOpacity-enter-active, .fadeOpacity-leave-active {
    transition: opacity .35s ease-out;
  }
  .fadeOpacity-enter, .fadeOpacity-leave-active {
    opacity: 0;
  }

  body {
    width: 80%;
    margin-left: 10%;
  }

  .basic-info {
    font-size: 16px;
    font-weight: 500;
    background-color: bisque;
    text-align: center;
    margin-top: 10px;
    border: medium solid lightgrey;
  }

  li {
    list-style: none;
  }

  .list-badge {
    width: 200px;
    background: white;
    -webkit-transition: background-color 2s; /* Safari */
    transition: background-color 2s;
    transition-duration: 2s;
    display: inline-block;
    margin: 20px;
    cursor: grab;
  }
  .list-badge:hover {
    background-color: rgb(248, 205, 153);
  }

  .badge-details {
    text-align: center;
    transition:all 3s ease;
  }
</style>
