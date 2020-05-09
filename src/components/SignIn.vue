<template>
  <form action="/" v-on:submit.prevent="">
    <fieldset>
      <label for="mail">Mail</label>
      <input type="email" id="mail" name="mail" v-model="email" />
      <label for="psw">Password</label>
      <input type="password" id="psw" name="password" v-model="password" />
      <button type="submit">Submit</button>
    </fieldset>
  </form>
</template>

<script>
export default {
  name: "SignIn",
  data() {
    return {
      email: "",
      password: ""
    };
  }
};
</script>

<style scoped lang="scss">
form {
  width: 40%;
  margin: 20px auto;
  font-weight: bold;
  font-size: 1.2em;
  color: gray;

  fieldset {
    padding: 20px;
    text-align: start;
    display: grid;

    & > * {
      margin: 7px 0;
    }

    input {
      width: 99%;
      padding: 5px;
    }

    button[type="submit"] {
      padding: 15px;
      border-radius: 5px;
      font-size: 0.8em;
      font-weight: bold;
      border: 1px solid gray;
      color: gray;
    }

    button[type="submit"]:hover {
      background-color: #4a1748;
      color: white;
      border: 1px solid #000;
    }
  }
}
</style>
