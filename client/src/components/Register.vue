<template>
  <div class="hello">
    <h1>Register</h1>
    <input 
      type="email" 
      name="email" 
      placeholder="Email"
      v-model="email">
    <br>
    <input 
      type="password" 
      name="password" 
      placeholder="password"
      v-model="password">
      <br>
      <button
        @click="register"
      >Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService';
export default {
  name: 'Register',
  data(){
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register(){
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      });
      console.log(response.data);
    }
  }
}
</script>

<style scoped lang="scss">
</style>
