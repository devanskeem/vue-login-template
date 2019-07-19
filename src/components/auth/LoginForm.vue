<template>
  <div
    class="form"
    v-bind:class="{'slide-right':(!register || register == 'start'), 'slide-left':(register === true)}"
  >
    <div class="form-container">
      <h1 v-bind:class="{'title-register':(!register), 'title-login':(register)}">{{title}}</h1>

      <form v-if="register" class="form-input">
        <input class="input" type="text" name="username" placeholder=" Username" />
        <input class="input" type="password" name="password" placeholder=" Password" />
        <button class='submit'>Submit</button>
      </form>
      <form v-else class="form-input">
        <input class="input" type="text" name="username" placeholder=" Username" />
        <input class="input" type="password" name="password" placeholder=" Password" />
        <input class="input" type="password" name="passConfirm" placeholder=" Confirm Password" />
        <button class='create'>Create</button>
      </form>
    </div>
  </div>
</template>


<script>
export default {
  name: "LoginSlider",
  props: ["register", "title"]
};
</script>

<style>
.form {
  z-index: 3;
  position: absolute;
  width: 55vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.slide-right {
  animation: slideRight 0.45s ease;
  animation-fill-mode: forwards;
}

.slide-left {
  animation: slideLeft 0.45s ease;
}

.form-container {
    margin-bottom: 300px;
    flex-direction: column;
    display: flex;
    align-items: center;

}

.title-register {
  color: rgb(0, 165, 215);
}

.title-login {
  color: rgb(21, 126, 255);
}

.form-input {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.submit {
    border: 2px solid rgb(21, 126, 255);
    width: 120px;
    height: 40px;
    border-radius: 25px;
    color: rgb(21, 126, 255);
    font-size: 15px;
    font-weight: 600;
    margin: 10px;
}
.submit:hover{
    background: rgb(21, 126, 255);
    color: white;
}


.create {
    border: 2px solid rgb(0, 165, 215);
    width: 120px;
    height: 40px;
    border-radius: 25px;
    color: rgb(0, 165, 215);
    font-size: 15px;
    font-weight: 600;
    margin: 10px;
}
.create:hover{
    background: rgb(0, 165, 215);
    color: white;
}
.input {
  border: none;
  height: 45px;
  width: 200px;
  background: whitesmoke;
  border-radius: 2px;
  margin: 5px;
  font-size: 16px;
  color: rgb(69, 69, 69);
}

.input::placeholder {
  font-size: 16px;
  margin: 0;
}

.input:focus, button:focus{
  outline: none;
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


