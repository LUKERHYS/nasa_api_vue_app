<template lang="html">
  <!-- <select>
    <option v-for="(asteroid, index) in asteroids" value="index">{{asteroids["near_earth_objects"]["2020-02-17"][0]["id"]}}</option>
  </select> -->
  <div>
  <ul>
    <li v-for="(asteroid, index) in asteroids">{{asteroid["near_earth_objects"]["2020-02-20"]}}</li>
  </ul>
</div>

</template>

<script>
export default {
  name: 'asteroid-container',
  props: ['asteroids', 'date'],
  circleWidth: "50px",
  asteriod_diameter: 0,
  methods: {
    dynamic_circle: function(){
      asteriod_diameter = this.asteroids["near_earth_objects"]["2020-02-17"][0]["estimated_diameter"]["meters"]["estimated_diameter_max"];
      return this.asteroid_diameter;
    }
  }
}
</script>

<style lang="css" scoped>
li{
  border-radius: 50%;
  width: dynamic_circle();
  height: 50px;
  background-color: #ededed;
  list-style: none;
}
</style>
