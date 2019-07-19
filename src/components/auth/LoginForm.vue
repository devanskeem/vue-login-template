<template>
  <form
    class="form"
    v-bind:class="{'slide-right':(!register || register == 'start'), 'slide-left':(register === true)}"
  >
  <h1>{{title}}</h1>
    <input class='input' type="text" name='username' placeholder="username">
    <input class='input' type="text" name='username' placeholder="username">
    <input class='input' type="text" name='username' placeholder="username">
  </form>
</template>


<script>
export default {
  name: "LoginSlider",
  props: ['register', 'title']
};
</script>

<style>
.form {
    z-index: 3;
    position: absolute;
    width: 55vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.slide-right {
   animation: slideRight .45s ease-in-out;
    animation-fill-mode: forwards;
}
.slide-left{
    animation: slideLeft 0.45s ease-in-out;
}

@keyframes slideRight {
  0% {

  }
  100% {
    transform: translateX(45vw);
  }
}

 @keyframes slideLeft {
  0% {
    transform: translateX(45vw);
  }
  50% {
    width: 65vw;
  }
  100% {
    transform: translateX(0);
  }
}
</style>


