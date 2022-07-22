<template>
  <Navbar />
<section>
  <router-view/>  
</section>

</template>

<script>
import Navbar from "@/components/Navbar.vue";
export default{
components:{
  Navbar
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
section{
  width: 100% !important;
}

   body{
    min-height: 100vh;
    margin-top: 0;
    background-image: url('https://i.postimg.cc/HktzX627/books-g3ba765adb-1280.jpg');
    background-repeat: no-repeat;
    background-size: cover !important;
    background-image: linear-gradient(
        0deg,
        rgba(0, 0, 0, 0.5),
        rgba(0, 0, 0, 0.5)
      ),
      url(https://i.postimg.cc/HktzX627/books-g3ba765adb-1280.jpg);
    background-position: 70%;
  }

</style>
