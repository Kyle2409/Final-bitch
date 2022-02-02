<template>
  <Navbar/>
  
  <router-view/>
</template>

<script>
import Navbar from "@/components/Navbar.vue"
import Footer from "@/components/footer.vue"
export default {
  components: {
    Navbar,Footer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  /* color: #2c3e50; */
  
  /* height: 120vh; */
  /* padding: 300px; */
}
.myname{
  /* float: left; */
  padding: 29px;
}

.projects{
  /* padding-top: 115px; */
  text-align: center;
}
</style>
