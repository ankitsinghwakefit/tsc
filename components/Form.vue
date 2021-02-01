<template>
  <div>
    <div class="container mt-5 mb-5">
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
          label="Your Msg:"
          label-for="textarea"
        >
        <b-form-textarea
        
          id="textarea"
          v-model="form.msg"
          placeholder="Enter your Msg..."
          rows="3"
          max-rows="6"
        ></b-form-textarea></b-form-group>

        <b-button class="mt-4" type="submit" variant="primary">Submit</b-button>
      </b-form>
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
//   methods: {
//     onSubmit(event) {
//       event.preventDefault();
//       axios
//         .post("https://muktiv2.herokuapp.com/", {
//           name: this.form.name,
//           number: this.form.number,
//           msg: this.form.msg
//         })
//         .then(function(response) {
          
//           if(response.data == "done"){
//            alert("Thanks we will revert soon!")
//           }
          
//         })
//         .catch(function(error) {
//           alert("Error - Form not submitted!")
//         });
//         this.form.name = "";
//         this.form.number = "";
//         this.form.msg = "";
//     }
//   }
};
</script>