<template lang="html">
  <div>
    <table>
      <tr>
        <td>
          <u>Name</u>
        <td>
          <u>id</u>
        </td>
        <td>
          <u>Neo reference id</u>
        </td>
        <td>
          <u>NASA JPL URL</u>
        </td>
        <td>
          <u>Absolute Magnitude</u>
        </td>
      </tr>
      <tr>
        <td>
        {{asteroid["near_earth_objects"]["2020-02-17"][0]["name"]}}
        <td>
        {{asteroid["near_earth_objects"]["2020-02-17"][0]["id"]}}
        </td>
        <td>
        {{asteroid["near_earth_objects"]["2020-02-17"][0]["neo_reference_id"]}}
        </td>
        <td>
        {{asteroid["near_earth_objects"]["2020-02-17"][0]["nasa_jpl_url"]}}
        </td>
        <td>
          {{asteroid["near_earth_objects"]["2020-02-17"][0]["absolute_magnitude_h"]}}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "asteroid-detail",
  props: ["asteroid"]
}
</script>

<style lang="css" scoped>
div {
  display: flex;
  justify-content: space-between;
}
td {
  
}

</style>
