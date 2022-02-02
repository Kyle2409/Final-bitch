<template>
  <MDBFooter bg="dark" :text="['center', 'white']">
    <!-- Grid container -->
    <MDBContainer class="p-4 pb-0">
      <!-- Section: Social media -->
      <section class="mb-4">
        <!-- Facebook -->
       
        <!-- Linkedin -->
        <MDBBtn
          tag="a"
          outline="light"
          href="https://www.linkedin.com/in/kyle-mc-bryne-3b5420209/"
          floating
          class="m-1"
        >
          <MDBIcon iconStyle="fab" icon="linkedin-in"></MDBIcon>
        </MDBBtn>
        <!-- Github -->
        <MDBBtn
          tag="a"
          outline="light"
          href="https://github.com/Kyle2409"
          floating
          class="m-1"
        >
          <MDBIcon iconStyle="fab" icon="github"></MDBIcon>
        </MDBBtn>
      </section>
      <!-- Section: Social media -->
    </MDBContainer>
    <!-- Grid container -->
    <!-- Copyright -->
    <div
      class="text-center p-3"
      style="background-color: rgba(0, 0, 0, 0.2)"
    >
      © 2021 Copyright:
      <a class="text-white" href="https://mdbootstrap.com/"
        >Kyle Mc Bryne</a
      >
    </div>
    <!-- Copyright -->
  </MDBFooter>
</template>

<script>
  import { MDBFooter, MDBContainer, MDBRow, MDBCol, MDBBtn, MDBIcon } from 'mdb-vue-ui-kit';
  export default {
    components: {
      MDBFooter,
      MDBContainer,
      MDBRow,
      MDBCol,
      MDBBtn,
      MDBIcon
    },
  };
</script>