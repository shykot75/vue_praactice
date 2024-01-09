<template>
  <h4>This is Child </h4>
  <button v-on:click="getUser(user_name)">Send User Name</button>

</template>

<script>
export default {
  name: 'Child-',

  data(){
    return {
      user_name: "Peter Mia"
    }
  },
  props: {
    getUser: Function,
  },
}

</script>

<style scoped>

</style>