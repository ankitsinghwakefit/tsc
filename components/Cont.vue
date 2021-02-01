<template>
<div class="caroContainer" id="contact">
    <div class="myCarousal">
    <div class="intro">
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
          label="Support Required:"
          label-for="textarea"
        >
        <b-form-textarea
        
          id="textarea"
          v-model="form.msg"
          placeholder="Enter your Service..."
          rows="3"
          max-rows="6"
        ></b-form-textarea></b-form-group>

        <b-button class="mt-4" type="submit" variant="primary">Submit</b-button>
      </b-form>
    </div>
    </div>
</div>
</template>

<script>
const axios = require("axios");
export default {
  data() {
    return {
      form: {
        name: "",
        number: "",
        msg: "",
      }
    };
  },
  methods: {
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
    }
  }
};
</script>

<style scoped>
/* .caroContainer {
    height: 40vh !important;
    text-align: center;
    align-items: center;
} */
.myCarousal {
    background-image: url("~assets/contact.jpg");
  background-repeat: no-repeat;
  background-position: center;
    background-size: cover;
    height: 100%;
    display: flex;
     justify-content: center;
  align-items: center;
  /* text-align: center; */
}
.intro {
    color: #105ef0;
    background-color: #eee;
    opacity: .9;
    border-radius: 8px;
    padding: 20px;
    min-width: 600px;
    margin: 40px;
}
.intro:hover {opacity: 1;
transform: scale(1.1);
transition: 500ms linear; 
}
.button {
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 20px;
  margin: 8px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
  background-color: white; 
  color: #105ef0; 
  font-weight: bolder;
  border: 2px solid #105ef0;
  border-radius: 8px;
}

.button:hover {
  background-color: #105ef0;
  color: white;
}
@media only screen and (max-width: 800px) {
    .intro {
    font-size: 8px;
    border-radius: 8px;
    padding: 10px;
    margin: 10px;
    min-width: 600px;
    margin: 40px;
}
.intro:hover {opacity: 1;
transform: scale(1.1);
transition: 500ms linear; 
}
}
@media only screen and (max-width: 500px) {
    .intro {
    font-size: 8px;
    border-radius: 8px;
    padding: 10px;
    margin: 10px;
    min-width: 350px;
    margin: 40px;
}
.intro:hover {opacity: 1;
transform: scale(1.1);
transition: 500ms linear; 
}
}

</style>
