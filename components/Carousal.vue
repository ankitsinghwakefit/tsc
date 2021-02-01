<template>
<div class="caroContainer">
    <div class="myCarousal">
    <div class="intro">
        <h1>Research | Strategies | Investment Classes </h1>
        <!-- <b-row>
            <b-col xl="3" lg="3" md="3" sm="12">
                Research
            </b-col>
            <b-col xl="3" lg="3" md="3" sm="12">
                | Strategies
            </b-col>
            <b-col xl="3" lg="3" md="3" sm="12">
                | Investment Classes
            </b-col>
        </b-row> -->
        <button class="button" @click="getQuote">Get free classes!</button>
    </div>
    </div>
</div>
</template>

<script>
export default {
    methods: {
        getQuote(){
            this.$emit("showMod");
        }
    }
}
</script>

<style scoped>
.caroContainer {
    height: 85vh !important;
    text-align: center;
    align-items: center;
}
.myCarousal {
    background-image: url("~assets/hero2n.jpg");
  background-repeat: no-repeat;
  background-position: center;
    background-size: cover;
    height: 100%;
    display: flex;
     justify-content: center;
  align-items: center;
  text-align: center;
}
.intro {
    color: #105ef0;
    background-color: #eee;
    opacity: .9;
    border-radius: 8px;
    padding: 20px;
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
}
.intro:hover {opacity: 1;
transform: scale(1.1);
transition: 500ms linear; 
}
}

</style>
