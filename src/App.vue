<template>
  <div id="app">
    <div class="date picker">
      <label for="start-date">Pick a date:</label>
      <input type="date" name="start-date" value="start-date">
      <p>This date will return the selected date and the 7 days after.</p>
    </div>

    <label>Element Counter:</label>
    <asteroid-item :asteroid="asteroids"/>
    <asteroid-container :asteroids="asteroids"/>
    <asteroid-detail :asteroid="asteroids"/>
  </div>
</template>

<script>
import asteroidItem from './components/item.vue';
import asteroidContainer from './components/container.vue';
import asteroidDetail from './components/detail.vue';
export default {
  name: 'app',
  data(){
    return {
      start_date: '2020-02-17',
      end_date: '2020-02-21',
      dynamic_url: '',
      asteroids: []
    }
  },
  computed:{
    api_url: function(){
      return this.dynamic_url = `https://api.nasa.gov/neo/rest/v1/feed?start_date=${this.start_date}&end_date=${this.end_date}&api_key=6IY3daHDUnJwItCw1uTe2QYszPX7FEAgEmEpRZwv`;
    }
  },
  mounted(){
    fetch(this.api_url)
    .then(result => result.json())
    .then(payload => this.asteroids = payload)

  },
  components: {
    'asteroid-item': asteroidItem,
    'asteroid-container': asteroidContainer,
    'asteroid-detail': asteroidDetail
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
