<!-- Use preprocessors via the lang attribute! e.g. <template lang="pug"> -->
<template>
  <div id="app">
    <div class="main">
      <div class="input-group">
        <input :type="inputType" v-model="password" class="input" />
        <button class="input-group-icon" @click="togglePassword">
          {{ toggleBtnIcon }}
        </button>
      </div>
    </div>
    <a
      class="credits"
      target="_blank"
      href="https://vue-show-hide-password.netlify.app/"
    >
      Show/hide password with emoji built with Vue
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showPassword: false,
      password: "Your Secret",
    };
  },
  methods: {
    togglePassword() {
      this.showPassword = !this.showPassword;
    },
  },
  computed: {
    inputType() {
      return this.showPassword ? "text" : "password";
    },
    toggleBtnIcon() {
      return this.showPassword ? "🐵" : "🙈";
    },
  },
};
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
html,
body,
#app {
  height: 100%;
}
body {
  background-color: #e3e6f1;
}
body,
button,
input {
  font-family: "Poppins", sans-serif;
}
.main {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.input-group {
  display: inline-flex;
  background-color: #ffffff;
  align-items: center;
  border-radius: 0.5rem;
  overflow: hidden;
  font-size: 2rem;
  box-shadow: 0px 2px 4px 1px rgba(0, 0, 0, 0.25);
}
.input-group input {
  border: 0;
  padding: 1rem;
}
.input-group input:focus {
  outline: 0;
}
.input-group-icon {
  padding: 0.5rem;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  align-self: stretch;
  border: 0;
  background-color: inherit;
  cursor: pointer;
}
.credits {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  background-color: #212121;
  color: #ffffff;
  text-decoration: none;
  padding: 1rem;
  text-align: center;
}
</style>
