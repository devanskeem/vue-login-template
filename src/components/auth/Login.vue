<template>
  <div class="login-page">
    <LoginSlider
      v-on:slide="slide"
      v-bind:register="register"
      v-bind:greeting="greeting"
      v-bind:question="question"
      v-bind:buttonText="buttonText"
    />
    <LoginForm v-bind:register="register" 
             v-bind:title="title" />
  </div>
</template>

<script>
import LoginSlider from "./LoginSlider";
import LoginForm from "./LoginForm";
export default {
  name: "Login",
  components: {
    LoginSlider,
    LoginForm
  },
  methods: {
    slide() {
      this.register = !this.register;
      if (this.register) {
        this.greeting = "Welcome back!";
        this.question = "Don't have an account?";
        this.buttonText = "Create Account";
        this.title = 'Login'
      } else {
        this.greeting = "Welcome!";
        this.question = "Already have an account?";
        this.buttonText = "Login";
        this.title = 'Register'
      }
    }
  },
  data() {
    return {
      register: "start",
      greeting: "Welcome back!",
      question: "Don't have an account?",
      buttonText: "Create Account",
      title: 'Login'
    };
  }
};
</script>

<style>
.login-page {
  display: flex;
}
</style>


