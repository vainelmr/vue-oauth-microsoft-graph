<template>
    <div>
      <AsyncButton class="button" @click="signIn" >Sign In</AsyncButton>
      <div v-if="user">
        <p>Welcome, {{ user.name }}</p>
      </div>
    </div>
  </template>
  
  <script>
  import {signInAndGetUser} from '../lib/microsoftGraph.js';
  
  export default {
    name: 'SignInButton',
    data() {
      return {
        user: null
      };
    },
    methods: {
      async signIn() {
        try {
          const user = await signInAndGetUser();
          this.user = user;
        } catch (error) {
          console.error('Error during sign-in:', error);
        }
      }
    }
  };
  </script>

<style scoped>
    .button {
        margin: 20px;
        padding: 10px 20px;
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    
    .button:hover {
        background-color: #7cac7db3;
    }
    
    .welcome-message {
        margin-top: 20px;
        font-size: 1.2rem;
    }
</style>
  
  