<template>
  <nav>
    <router-link to="/">Register</router-link> |
    <router-link to="/users">Users</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
  nav {
    padding: 30px;
    background-color: rgb(99, 99, 99);
    position: fixed;
    top: 0;
    width: 100%;
  }
  
  nav a {
    font-weight: bold;
    color: rgba(255, 255, 255, 0.966);
    text-decoration: none;
    margin: 1%;
    padding: 10px;
  background-color: #4f4f4f;
  border-radius: 20px;
  }
  
  nav a.router-link-exact-active {
    background-color: #ffc801;
    color: rgb(109, 109, 109);
  }
</style>
