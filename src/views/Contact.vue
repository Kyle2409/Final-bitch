<template>
<!-- <Navbar/> -->
 <section id="contact" >
 
    <div class="contact container">
      <div>
        <h1 class="section-title">Contact <span>info</span></h1>
      </div>
      <form @submit.prevent="handleSubmit">
        <label>Name:</label>
        <input type="name" v-model="name" required>
        <label>Email:</label>
        <input type= "email" v-model="email" required>
        <label>Message:</label>
        <textarea name="messsage" id="" cols="40" rows="10" required v-model="message"></textarea>
        <button type="submit">Send Message</button>
      </form>
      <div class="contact-items">
        <div class="contact-item">
          <div class="icon"><img src="https://img.icons8.com/bubbles/100/000000/phone.png" /></div>
          <div class="contact-info">
            <h1>Phone Number:</h1>
            <h2>0769815243</h2>
          </div>
        </div>
        <div class="contact-item">
          <div class="icon"><img src="https://img.icons8.com/bubbles/100/000000/new-post.png" /></div>
          <div class="contact-info">
            <h1>Email</h1>
            <h2>kylemcb.24@gmail.com</h2>
          </div>
        </div>
      <div class="contact-item">
          <div class="icon"><img src="https://img.icons8.com/bubbles/100/000000/map-marker.png" /></div>
          <div class="contact-info">
            <h1>Address</h1>
            <h2>314 Imam Haron Road,Landsdown ,7779</h2>
          </div>
        </div>
      </div>
    
    </div>
   
          
  </section>
  <Footer/>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Footer from "@/components/footer.vue"
export default {
  name: 'Contact',
  components: {
  Navbar,Footer
  },
  data() {
    return{
    name: "",
    email: "",
    message: "",
    }
},
methods: {
    handleSubmit(){
        console.log("Form has been submitted");
        console.log(this.name);
        console.log(this.email);
        console.log(this.message);

        fetch("https://backend-kyle24.herokuapp.com/contact", {
  method: "POST",
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
    }
    
},
}
</script>

<style>
.contact{
  display: flex !important;
}
#contact .contact {
	flex-direction: column;
	max-width: 1200px;
	margin: 0 auto;
	width: 90%;
}
#contact .contact-items {
	/* max-width: 400px; */
	width: 100%;
}
#contact .contact-item {
	width: 80%;
	
	padding: 20px;
	text-align: center;
	border-radius: 10px;
	padding: 30px;
	margin: 30px;
  margin-left: 100px !important;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	box-shadow: 0px 0px 18px 0 #0000002c;
	transition: 0.3s ease box-shadow;
}
#contact .contact-item:hover {
	box-shadow: 0px 0px 5px 0 #0000002c;
}
#contact .icon {
	width: 70px;
	margin: 0 auto;
	margin-bottom: 10px;
}
#contact .contact-info h1 {
	color: white;
	font-size: 2.5rem;
	font-weight: 500;
	margin-bottom: 5px;
}
#contact p{
  color: black
}
#contact .contact-info h2 {
	color: white;
	font-size: 1.3rem;
	line-height: 2rem;
	font-weight: 500;
}
#contact .contact {
		flex-direction: column;
		padding: 100px 0;
		align-items: center;
		justify-content: center;
		min-width: 20vh;
	}
	#contact .contact-items {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		margin: 0;
	}
	#contact .contact-item {
		width: 30%;
		margin: 0;
		flex-direction: row;
	}
	#contact .contact-item .icon {
		height: 100px;
		width: 100px;
	}
	#contact .contact-item .icon img {
		object-fit: contain;
    width: 90px !important;
    height: 90px !important;
	}
	#contact .contact-item .contact-info {
		width: 100%;
		text-align: left;
		padding-left: 20px;
	}
	#footer p {
		color: white;
		font-size: 1.3rem;
		text-align: center;
	}
    form {
	  opacity: 0.8;
	  border-radius: 50px;
    width: 400px;
    padding: 25px;
    margin: 25px;
	
	transition: width .5s ease 0s, right .5s ease 0s;
	box-shadow: 0px 0px 18px 0 #0000002c;
	transition: 0.3s ease box-shadow;
	
    }
    .fas {
    margin: 25px 10px 0;
    font-size: 72px;
    color: #fff;
    }
    .fa-envelope {
    transform: rotate(-20deg);
    }
    .fa-at , .fa-mail-bulk{
    transform: rotate(10deg);
    }
    input, textarea {
    width: calc(100% - 18px);
    padding: 8px;
    margin-bottom: 20px;
    border: 1px solid #1c87c9;
    outline: none;
    border-radius: 10px;
    }
    input::placeholder {
    color: #666;
    } 
    
    @media (min-width: 568px) {
    .main-block {
    flex-direction: row;
	}
}
#contact {
	background-image: url(https://i.postimg.cc/qRHRfhwy/christopher-sardegna-b-Sm-Kli4-OTIY-unsplash.jpg);
	background-size: cover;
}
.bn30 {
	outline: none;

}
*{
  color: black !important;
}
.contact container{
    align-items: center;
    justify-content: center;
}
</style>