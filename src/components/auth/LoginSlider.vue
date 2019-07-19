<template>
  <div class="slider" v-bind:class="{'slide-right':(register === true), 'slide-left':(!register || register == 'start')}">
    <h1 class="greeting">{{greeting}}</h1>
    <p class="question">{{question}}</p>
    <button class="register-button" @click="$emit('slide')">{{buttonText}}</button>
  </div>
</template>


<script>
export default {
  name: "LoginSlider",
  props: ["register", "greeting", "question", "buttonText"],
  data() {
    if (this.register) {
        this.greeting = "Welcome back!";
        this.question = "Don't have an account?";
        this.buttonText = "Create Account";
      } else {
        this.greeting = "Welcome!";
        this.question = "Already have an account?";
        this.buttonText = "Login";
    }
    return {
      register: 'start',
      greeting: "Welcome back!",
      question: "Don't have an account?",
      buttonText: "Create Account"
    };
  }
};
</script>

<style scoped>
.slider {
  z-index: 5;
  height: 100vh;
  width: 45vw;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background: rgb(21, 126, 255);
}
.slide-right {
  animation: scaleNSlideRight .45s ease;
  animation-fill-mode: forwards;
}
.slide-left + .register-button{
  animation: scaleNSlideLeft 0.45s ease;
}
.greeting {
  color: whitesmoke;
  margin: 5px;
  font-size: 55px;
  font-weight: 700;
}
.question {
  color: whitesmoke;
  font-size: 25px;
  margin: 5px;
}
.register-button {
  border: 1px solid whitesmoke;
  height: 3em;
  width: 10em;
  background: none;
  border-radius: 3em;
  color: whitesmoke;
  font-weight: 600;
  font-size: 15px;
  margin: 10px 0 250px 0;
}
.register-button:hover {
  background: whitesmoke;
  color: rgb(21, 126, 255);
}

.register-button:focus {
  outline: none;
}

@keyframes scaleNSlideRight {
  0% {
    width: 45vw;
    background: rgb(21, 126, 255);

  }
  50% {
    width: 65vw;
  }
  100% {
    width: 45vw;
    transform: translateX(55vw);
    background: rgb(0, 165, 215);

  }
}
  @keyframes scaleNSlideLeft {
  0% {
    transform: translateX(55vw);
    width: 45vw;
    background: rgb(0, 165, 215);
  }
  50% {
    width: 65vw;
  }
  100% {
    width: 45vw;
    background: rgb(21, 126, 255);
    transform: translateX(0);
  }
}
</style>


