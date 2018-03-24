<template>
  <div class="hello">
    <h1>Register</h1>
    <input
    type="email"
    name="email"
    v-model="email"
    placeholder="Email" />
    <br>
    <input
    type="password"
    name="password"
    v-model="password"
    placeholder="Password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from "@/services/AuthenticationService";
export default {
  name: 'register',
  data () {
    return {
      email: '',
      password: ''
    }
  },

  watch: {

  },
  methods: {
   async register() {
    const response = await  AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  },
  mounted() {
    setTimeout(() => {
      this.email = 'hello world'
    }, 2000)
  }
}
</script>
