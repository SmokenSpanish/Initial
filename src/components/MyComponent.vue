<template>
  <div class="root">
    <label></label>
      Введите email:
      <input
        type="email"
        :value="email"
        @input="emailInput($event.target.value)"
      />
    <label></label>
      Введите пароль:
      <input
        type="password"
        :value="password"
        @input="passwordInput($event.target.value)"
      />
    

    email: {{ email }} password: {{ password }}
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      email: "FUCK",
      password: "BULLSHIT",
    };
  },
  methods: {
    emailInput(value) {
      this.email = value;
    },

    passwordInput(value) {
      this.password = value;
    },
  },
};
</script>

<style>
.root {
    padding: 15px;
}

input,
select {
  display: block;
  padding: 10px 6px;
  width: 30%;
  box-sizing: border-box;
  border: 1px solid #ddd;
  color: rgb(165, 148, 148);
}

label {
  color: rgb(122, 121, 121);
  display: inline-block;
  margin: 12px 0 12px;
  font-size: 0.8em;
}
</style>