<template>
  <h4>This is Child Component from ChildComponent.vue page</h4>
  <p>{{ text }}</p>
  <p>{{ childUser.name }}-- {{ childUser.address}}</p>
  <button v-on:click="parentFun">call function</button>

</template>

<script>
export default {
  name: 'ChildComponent',
  props: {
    text: String,
    childUser: Object,
    parentFun: Function,
  },
}

</script>

<style scoped>

</style>