<template>
  <form action="/" v-on:submit.prevent="">
    <fieldset>
      <label for="mail">Mail</label>
      <input type="email" id="mail" name="mail" v-model="email" />
      <label for="age">Your Age</label>
      <input type="number" id="age" name="age" v-model="age" />
      <label for="psw">Password</label>
      <input type="password" id="psw" name="password" v-model="password" />
      <label for="psw2">Confirm Password</label>
      <input
        type="password"
        id="psw2"
        name="confirmedPassword"
        v-model="confirmedPassword"
      />
      <label for="country">Country</label>
      <select name="country" id="country" v-model="country">
        <option value="USA">USA</option>
        <option value="Italy">Italy</option>
        <option value="Spain">Spain</option>
        <option value="France">France</option>
        <option value="Germany">Germany</option>
      </select>
      <p>Add some Hobbies</p>
      <button class="hobby" type="button" @click="addHobby">Add Hobby</button>
      <div class="hobby-list">
        <div
          class="input"
          v-for="(hobbyInput, index) in hobbyInputs"
          :key="hobbyInput.id"
        >
          <label :for="hobbyInput.id">Hobby #{{ index }}</label>
          <input type="text" :id="hobbyInput.id" v-model="hobbyInput.value" />
          <button type="button" @click="deleteHobby(hobbyInput.id)">X</button>
        </div>
      </div>
      <label class="policy">
        <input type="checkbox" id="termsOfUse" v-model="terms" />
        <span class="checkbox"></span>
        Accept Terms of Use
      </label>
      <button type="submit">Submit</button>
    </fieldset>
  </form>
</template>

<script>
export default {
  name: "SignUp",
  data() {
    return {
      email: "",
      age: null,
      password: "",
      confirmedPassword: "",
      country: "Italy",
      hobbyInputs: [],
      terms: false
    };
  },
  methods: {
    addHobby() {
      const newHobby = {
        id: Math.random() * 1000,
        value: ""
      };
      this.hobbyInputs.push(newHobby);
    },
    deleteHobby(id) {
      this.hobbyInputs = this.hobbyInputs.filter(hobby => hobby.id !== id);
    },
    submit() {
      const formData = {
        email: this.email,
        age: this.age,
        password: this.password,
        confirmedPassword: this.confirmedPassword,
        country: this.country,
        hobbies: this.hobbyInputs.map(hobby => hobby.value),
        terms: this.terms
      };
      console.log(formData);
    }
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

    p {
      color: black;
    }

    button.hobby {
      padding: 7px;
      border-radius: 5px;
      background-color: #4a1748;
      color: white;
      font-size: 0.8em;
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
    label.policy {
      padding: 20px 0;
      margin: 0;
      position: relative;
      display: flex;
      align-items: center;

      input {
        position: absolute;
        width: 0;
        height: 0;
        opacity: 0;
      }

      .checkbox {
        width: 14px;
        height: 14px;
        border: 1px solid lightgray;
        margin-right: 15px;
        padding: 1px;
        position: relative;
      }

      .checkbox::after {
        content: "";
        width: 4px;
        height: 6px;
        border: solid white;
        border-width: 0 2px 2px 0;
        position: absolute;
        left: 5px;
        top: 4px;
        transform: rotate(45deg);
      }

      input:checked + .checkbox {
        background-color: lightseagreen;
        border: 1px solid lightseagreen;
      }
    }

    .hobby-list {
      input {
        width: 80%;
        border: 0.5px solid #4a1748;
        background-color: lightgray;
      }

      button {
        margin: 0 10px;
        padding: 5px;
        background-color: #4a1748;
        border: 1px solid #000;
        color: white;
      }
    }
  }
}
</style>
