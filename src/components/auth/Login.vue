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
        this.title = 'Sign in to Chat'
      } else {
        this.greeting = "Welcome!";
        this.question = "Already have an account?";
        this.buttonText = "Login";
        this.title = 'Create an Account'
      }
    }
  },
  data() {
    return {
      register: true,
      greeting: "Welcome back!",
      question: "Don't have an account?",
      buttonText: "Create an Account",
      title: 'Sign in to Chat'
    };
  }
};
</script>

<style>
.login-page {
  display: flex;
}
</style>


