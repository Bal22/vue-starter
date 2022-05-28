<template>
  <div id = "app">
    <h1>e-mail:  {{email}}</h1>
    <input type="text" v-model="email">

  </div>
</template>

<script>


export default {
  data() {
    return {
      email: '',
      password: ''
    };
  }

}
</script>

<style>

</style>
