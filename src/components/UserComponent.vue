<template>
  <h5>{{comData.com_name}}--{{comData.com_email}}</h5>
<button v-on:click="getComName(comData.com_name)">Alert Name</button>
</template>

<script>

export default {
  name: "UserComponent",
  props: {
    comData: Object,
    getComName: Function,
  },


}

</script>

<style>

</style>