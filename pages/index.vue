<template>
<div>
    <Navbar />
    <Carousal @showMod="getQuote" />
    <!-- -------------------------- modal --------------------------------- -->

  <div v-if="form.showModal" class="myModal">
    <!-- <particles-bg type="circle" :bg="true" /> -->
    <div class="modalChild">
    <b-form @submit="onSubmit">
        <b-form-group id="input-group-1" label="Name:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.name"
            type="text"
            placeholder="Enter Name"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-2"
          label="Your Number:"
          label-for="input-2"
        >
          <b-form-input
            id="input-2"
            v-model="form.number"
            type="number"
            placeholder="Enter Number"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-3"
          label="Required Service:"
          label-for="textarea"
        >
        <b-form-textarea
        
          id="textarea"
          v-model="form.msg"
          placeholder="Trading / Learning ..."
          rows="3"
          max-rows="6"
        ></b-form-textarea></b-form-group>

        <b-button class="mt-4" type="submit" variant="primary">Submit</b-button>
        <b-button class="mt-4" @click="closeModal" variant="primary">Close</b-button>
      </b-form>
    </div>
  </div>
    <Intro />
    <Homeservice />
    <Cont />
    <Footer />
  </div>
</template>

<script>
const axios = require("axios");
export default {
  data() {
    return {
      form : {
        name: "",
        number: "",
        mag: "",
         showModal : false
      }
    };
  },
  props: [""],
  methods: {
    getQuote(){
      this.form.showModal = true;
    },
    closeModal(){
      this.form.showModal = false;
    },
    onSubmit(event) {
      event.preventDefault();
      axios
        .post("https://muktiv2.herokuapp.com/", {
          name: this.form.name+"stock",
          number: this.form.number,
          msg: this.form.msg
        })
        .then(function(response) {
          
          if(response.data == "done"){
           alert("Thanks we will revert soon!")
          }
          
        })
        .catch(function(error) {
          alert("Error - Form not submitted!")
        });
        this.form.name = "";
        this.form.number = "";
        this.form.msg = "";
        // this.form.modalShow = true;
        this.form.showModal = false;
    }
  }
}
</script>

<style>
html {
  scroll-behavior: smooth;
}
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
} */

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
  .myModal{
  z-index: 990;
  position: fixed;
   top: 0%;
  left: 0%;
  width: 100vw;
  height: 100vh;
  background-color: #434246;
  opacity: .9;
}
.modalChild {
  z-index: 980;
  transform: translate(-50%, -50%);
  position: fixed;
  top: 50%;
  left: 50%;
  width: 40%;
   padding: 17px;
   border-radius: 8px;
   opacity: 1.2;
   /* font-size: 20px; */
   font-weight: bolder;
  background-color: #ffffff;
}
@media only screen and (max-width: 768px) {
  .myModal{
  z-index: 990;
  position: fixed;
   top: 0%;
  left: 0%;
  width: 100vw;
  height: 100vh;
  background-color: #434246;
  opacity: .9;
}
.modalChild {
  z-index: 980;
  transform: translate(-50%, -50%);
  position: fixed;
  top: 50%;
  left: 50%;
  width: 90%;
  
   padding: 17px;
   border-radius: 8px;
   opacity: 1.2;
   /* font-size: 20px; */
   font-weight: bolder;
  background-color: #ffffff;
}
}
</style>
