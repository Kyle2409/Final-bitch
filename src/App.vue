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
  },
  methods:{
handleSubmit(){
  console.log(this.email,this.name,this.message)
  fetch('http://localhost:5000/contact', {
  method: 'POST',
  body: JSON.stringify({
    name:this.name,
    email:this.email,
    message:this.message,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => alert(json.msg))
  .catch((e) => alert(e.msg));
},
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
