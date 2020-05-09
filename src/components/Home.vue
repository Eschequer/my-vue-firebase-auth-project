<template>
  <div class="component">
    <h1 class="">Time to learn something new!</h1>
    <div class="buttons">
      <router-link to="/signUp" tag="button">Sign Up</router-link>
      <router-link to="/signIn" tag="button">Sign In</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home"
};
</script>

<style scoped lang="scss">
.component {
  min-width: 200px;

  .buttons {
    display: flex;
    justify-content: center;

    button {
      padding: 20px;
    }

    button:nth-child(1) {
      margin-right: 35px;
    }

    button:hover {
      background-color: rgb(74, 23, 72);
      color: white;
    }
  }
}
</style>
