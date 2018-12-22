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

      <div class="badges">
        <li v-for="(badge, index) in profile.topBadges" :key="index">
          <div>
            <h3>{{badge.badgeType}}</h3>
            <img v-bind:src="badge.image50px">
            <div>{{badge.shortDescription}}</div>
            {{badge}}
          </div>
        </li>
      </div>

    </div>
  </section>
</template>

<script>

export default {
  transition: 'fadeOpacity',
  async asyncData({ app, params, error }) {
    console.log(app)
    let profile = await app.$axios.$get('https://tender-wescoff-5cd4a9.netlify.com/userProfile.json')
    return { profile }
  }
}
</script>

<style>
  .fadeOpacity-enter-active, .fadeOpacity-leave-active {
    transition: opacity .35s ease-out;
  }

  .fadeOpacity-enter, .fadeOpacity-leave-active {
    opacity: 0;
  }

  .basic-info {
    font-size: 16px;
    font-weight: 500;
    background-color: bisque;
    text-align: center;
  }

  li {
    list-style: none;
    display: inline-block;
    padding: 20px;
  }
</style>
