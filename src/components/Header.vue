<template>
  <nav class="">
    <router-link to="/" exact href="#">Home</router-link>
    <router-link to="/signUp" href="#">Sign Up</router-link>
    <router-link to="/signIn" href="#">Sign In</router-link>
    <router-link to="/dashboard" href="#">Dashboard</router-link>
  </nav>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped lang="scss">
nav {
  background-color: rgb(74, 23, 72);
  display: flex;
  padding: 10px;

  a {
    color: white;
    text-decoration: none;
    padding: 15px;
    font-weight: bold;
    font-size: 1.2em;
  }

  a:nth-child(2) {
    margin-left: auto;
  }

  a:hover {
    color: #8f2c18;
  }
}

@media screen and (max-width: 768px) {
  nav {
    display: block;
    min-width: 200px;

    a {
      display: block;
    }
  }
}
</style>
