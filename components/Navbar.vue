<template>
<div class="navColor">
  <div class="container">
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <div>
        <!-- Just an image -->
        <b-navbar variant="faded" type="light">
          <b-navbar-brand to="/">
          <b-button class="logoresize">
        <i class="fas fa-chart-line"></i> Stocksala
      </b-button>
            <!-- <img class="logoresize" src="~/assets/logo2.jpg" alt="Mukti" /> -->
          </b-navbar-brand>
        </b-navbar>
      </div>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto myclassone">
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="#about">About</b-nav-item>
           <b-nav-item to="#services">Services</b-nav-item>
          <b-nav-item to="#contact">Contact</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
  </div>
</template>


<style scoped>
.navColor {
    background-color: #5577B4 ;
}
.nav-item {
    color: white !important;
}
.logoresize {
    color: aliceblue !important;
    font-size: 35px;
    background-color: rgb(62, 209, 32);
}
.navbar-dark .navbar-nav .nav-link{
      
      font-weight: bolder;
      margin-right: 25px!important;
      font-size: 22px!important;
    }
.navbar.navbar-dark.bg-dark {
  background-color: #5577B4 !important;
}
@media only screen and (max-width: 800px) {
    .logoresize {
    color: aliceblue !important;
    font-size: 25px;
}
}
</style>