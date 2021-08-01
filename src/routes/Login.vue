<template>
  <h1>Login</h1>
  <div
    class="card"
    style="width: 20rem;">
    <div class="card-body">
      <form @submit="login">
        <div class="mb-3">
          <label
            for="exampleInputEmail1"
            class="form-label">Email ID</label>
          <input
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp" />
          <div
            id="emailHelp"
            class="form-text">
            Email ID를 입력하세요
          </div>
        </div>
        <div class="mb-3">
          <label
            for="exampleInputPassword1"
            class="form-label">Password</label>
          <input
            type="password"
            class="form-control"
            id="exampleInputPassword1" />
        </div>
        <button
          type="submit"
          class="btn btn-primary">
          Sign In
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import {authService} from "../firebase/fb.js";

export default {
  name: "Login",
  data() {
    return {
      email:'',
      password:'',
      errMsg: ''
    }
  },
  computed:{},
  methods: {
    async login(e) {
      e.preventDefault();
      try {
        let data = await authService.signInWithEmailAndPassword(this.email, this.password);
        console.log(data);
      } catch (error) {
        console.dir(error)
      }
    }
  }
}
</script>

<style scoped>

</style>