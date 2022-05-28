<template>
  <div id = "app">

    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <h1>Twój e-mail:  {{email}}</h1>

    <div v-if="!authenticatedUsername">
    <login-form @login="login($event)" button-label="Wejdź"></login-form>
    <login-form @login="login($event)" button-label="Wleć"></login-form>
    <login-form @login="login($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    </div>


    <!--
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else class="red">Twój adres e-mail jest stanowczo za długi.</div>
    <input @keyup.enter = alertMyEmail() type = "email" v-model="email">
    -->

    <div v-if="authenticatedUsername == false">
      <h3>Zaloguj się e-mailem {{email}}</h3>
      <input type="email" v-model="email" >
      <button @click="login()"> Wchodzę</button>
    </div>

    <div v-if="authenticatedUsername == true">
      <h3>Witaj {{email}}</h3>
      <button @click="logout()">Wyloguj</button>
    </div>

    <!-- <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button> -->


  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";


export default {

  components: {LoginForm},

  data() {
    return {
      email: '',
      authenticatedUsername: false,
    };
  },





  methods: {
    alertMyEmail() {
      alert(this.email);
    }
    ,
    logout() {
      this.authenticatedUsername = false;
      this.email = "";
    },

    login() {
      this.authenticatedUsername = true;
    }
  }
}

</script>

<style>

.red { color: red; }

</style>
