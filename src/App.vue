<template>
  <div id = "app">

    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <h1>Twój e-mail:  {{email}}</h1>

    <!--
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else class="red">Twój adres e-mail jest stanowczo za długi.</div>
    <input @keyup.enter = alertMyEmail() type = "email" v-model="email">
    -->

    <div v-if="logged == false">
      <h3>Zaloguj się e-mailem {{email}}</h3>
      <input type="email" v-model="email" >
      <button @click="login()"> Wchodzę</button>
    </div>

    <div v-if="logged == true">
      <h3>Witaj {{email}}</h3>
      <button @click="logout()">Wyloguj</button>
    </div>

    <!-- <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button> -->


  </div>
</template>

<script>

export default {
  data() {
    return {
      email: '',
      logged: false
    };
  },

  methods: {
    alertMyEmail() {
      alert(this.email);
    }
    ,

    logout() {
      this.logged = false;
      this.email = "";
    },

    login() {
      this.logged = true;
    }
  }
}

</script>

<style>

.red { color: red; }

</style>
