<template>
  <div class="sign-up">
    <h3>Create a new account</h3>
    <v-text-field
      v-model="email" 
      type="email" 
      class="input" 
      placeholder="Email" 
      required/>
    <br>
    <v-text-field
      v-model="password"
      type="password" 
      class="input" 
      placeholder="Password" 
      required/>
    <br>
    <v-btn v-on:click="signUp" class="button">Sign Up!</v-btn>
    <button class="button">
      <router-link to="/login">
        Back
      </router-link>
    </button>
  </div>
</template>


<script>
import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

export default {
  name: 'signup',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    signUp () {
      const auth = getAuth();
      createUserWithEmailAndPassword(auth, this.email, this.password)
      .then((user) => {
          this.$router.replace('/home')
        }).catch((err) => {
          alert(err.message)
        });
      }
    }
  }
</script>