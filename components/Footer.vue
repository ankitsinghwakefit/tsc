<template>
<div class="footer-container">
  
    <div class="footer-child">
        <div class="child-One">
            <h2>Contact</h2>
            <p>Stocksala</p>
            <p>Thehr, ward no -15</p>
            <p>Vpo-khaniyara khas, Kangra</p>
            <p>Himachal Pradesh - 176218</p>
        </div>
        <div class="child-One">
            <p>Tel: +91 98997 12768</p>
            <!-- <p>Email: muktilisten@gmail.com</p> -->
            <!-- <p>Book a Consultation.</p> -->
           <span class="indian">Proudly Indian   </span><b-img src="~/assets/in.png" width="64" alt="placeholder"></b-img> <span class="maataram"> Vande Mataram.</span>
        </div>
        <div class="child-One">
            <p>Suscribe to our new offers.
            </p>
            <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Email"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Suscribe</b-button>
        </b-nav-form>
        </div>
    </div>
</div>
</template>

<style scoped>
.footer-container {
    width: 100%;
    background-color: #AB9856;
    padding-top: 50px;
    padding-bottom: 50px;
}
.footer-child {
    width: 80%;
    margin: 0 auto;
    display: flex;
  justify-content: center;
  align-items: center;
  
}
.child-One {
    width: 100%;
}
@media only screen and (max-width: 700px) { 
   .footer-child {
    margin: 0 auto;
    display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
}
@media only screen and (max-width: 380px) { 
    .footer-container {
    width: 100%;
    background-color: #AB9856;
    padding-top: 50px;
    padding-bottom: 50px;
}
   .footer-child {
    margin: 0 auto;
    display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
}
.indian {
  color: rgb(51, 51, 160);
  font-weight: bolder;
}
.maataram {
  color: white;
  font-weight: bolder;
}
</style>
