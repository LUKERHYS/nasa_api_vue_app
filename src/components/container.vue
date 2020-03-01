<template lang="html">
  <!-- <select>
    <option v-for="(asteroid, index) in asteroids" value="index">{{asteroids["near_earth_objects"]["2020-02-17"][0]["id"]}}</option>
  </select> -->
  <div>
  <ul class="cicrle">
    {{asteroid["near_earth_objects"]["2020-02-17"][0]["name"]}}
    <li v-for="(asteroid, index) in asteroids"></li>
  </ul>
</div>

</template>

<script>
export default {
  name: 'asteroid-container',
  props: ['asteroids'],
  circleWidth: "50px",
  asteriod_diameter: 0,
  computed: {
    dynamic_circle: function(){
      asteriod_diameter = this.asteroids["near_earth_objects"]["2020-02-17"][0]["estimated_diameter"]["meters"]["estimated_diameter_max"];
    }
  }
}
</script>

<style lang="css" scoped>
li{
  border-radius: 50%;
  width: this.asteriod_diameter px;
  height: this.asteriod_diameter px;
  background-color: #ededed;
  list-style: none;
}
</style>
