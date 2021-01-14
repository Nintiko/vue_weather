<template>
  <div id="app">
    <Container :weather="weather" />
  </div>
</template>

<script>
import Container from "./components/Сontainer.vue";
export default {
  name: "App",
  components: {
    Container,
  },
  data() {
    return {
      weather: {
        TemperatureReal: -2,
        TemperatureFeel: -3.5,
        HumidityVal: 25,
        WindVal: 13,
      }
    }
  },
  methods:{
    getWeatherInfo(){
      this.axios.get('http://37.77.104.246/api/weather/temp.php')
        .then((response)=>{
          this.weather.TemperatureReal = response.data;
        });
      this.axios.get('http://37.77.104.246/api/weather/feel.php')
        .then((response)=>{
          this.weather.TemperatureFeel = response.data;
        });
      this.axios.get('http://37.77.104.246/api/weather/humidity.php')
        .then((response)=>{
          this.weather.HumidityVal = response.data;
        });
      this.axios.get('http://37.77.104.246/api/weather/wind.php')
        .then((response)=>{
          this.weather.WindVal = response.data;
        });
    }
  },
  mounted(){
    this.getWeatherInfo();
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
}

#app {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background: rgb(244, 123, 186);
  background: linear-gradient(
    -25deg,
    rgba(244, 123, 186, 0.5) 20%,
    rgba(90, 95, 245, 0.5) 80%
  );
}
</style>
