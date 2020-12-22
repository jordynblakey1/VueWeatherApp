<template>
  <div class="temp">
<p> Chicago </p>

   {{weather}}
  °F

  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data() {
    return {
    weather : "" ,
    
  
    };
  }, 

  mounted() {
    axios.get('https://api.openweathermap.org/data/2.5/weather?q=Chicago&units=imperial&appid=*******************').
    then(response => (this.weather = response.data.main.temp));
    this.cityName = this.weather.main.temp; 
   
    //const cityWeather = JSON.parse(this.weather);
    //this.cityName = this.weather.main.temp;
    //console.log(cityWeather.name); 
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.temp {
  background-color: cornsilk;
  padding: 20px;
  margin: 40px;
  max-width: 100%;
  min-width: 50%;
  height: 90px;
}
</style>
