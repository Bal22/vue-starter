<template>
  <div>
    <label>Zaloguj się e-mailem</label>
    <input type="email" v-model="email">
    <button @click="login()">{{ buttonLabel }}</button>
  </div>
</template>

<script>
export default {
  
  props: ['buttonLabel'],

  data() {
    return {
      email: ''
    }
  },

  mounted() {
    if (!this.buttonLabel) {
      this.buttonLabel = 'Zaloguj się';
    }
  },

  methods: {
    login() {
      this.$emit('login', this.email);
    }

  }
}
</script>