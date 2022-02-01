<template>
<Navbar/>
  <h1>Projects</h1>
  <div class="projects" v-if="Projects.length">
    <div v-for="Project of Projects" :key="Project.id" class="Project">
      <MDBCard>
        <a v-mdb-ripple="{ color: 'light' }">
          <MDBCardImg
            :src="Project.image"
            top
            alt="..."
          />
        </a>
        <MDBCardBody>
          <MDBCardTitle>{{ Project.title }}</MDBCardTitle>
          <MDBCardText>
            {{Project.details}}
          </MDBCardText>
          <MDBBtn tag="a" target="_blank" :href="Projects.github" color="danger">Github</MDBBtn>
          <MDBBtn tag="a" href="#!" color="danger">Live</MDBBtn>
        </MDBCardBody>
      </MDBCard>
    </div>
  </div>

  
</template>

<script>
import {
  MDBCard,
  MDBCardBody,
  MDBCardTitle,
  MDBCardText,
  MDBCardImg,
  MDBBtn,
  mdbRipple,
} from "mdb-vue-ui-kit";
export default {
  components: {
    MDBCard,
    MDBCardBody,
    MDBCardTitle,
    MDBCardText,
    MDBCardImg,
    MDBBtn,
  },
  data() {
    return {
      Projects: [],
    };
  },
  mounted() {
    fetch("  http://localhost:3000/Projects")
      .then((res) => res.json())
      .then((data) => (this.Projects = data))
      .catch((err) => console.log(err.message));
  },

  directives: {
    mdbRipple,
  },
};
</script>

<style>
.projects {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  justify-content: center;
  align-items: center;
  text-align: center;
  grid-gap: 1rem;
  padding: 1rem 80px;
  font-size: 1.2rem;

}
.img {
  width: 300px;
  height: 300px;
}
</style>