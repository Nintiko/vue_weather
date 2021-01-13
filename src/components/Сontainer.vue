<template>
  <div class="informer-container">
    <Temperature :real="weather.TemperatureReal" :feel="weather.TemperatureFeel" />
    <FlexBreak />
    <Humidity :val="weather.HumidityVal" />
    <VerticalDivider />
    <Wind :val="weather.WindVal" />
  </div>
</template>

<script>
import Temperature from "./Temperature.vue";
import FlexBreak from "./FlexBreak.vue";
import Humidity from "./Humidity.vue";
import VerticalDivider from "./VerticalDivider.vue";
import Wind from "./Wind.vue";

export default {
  name: "Container",
  props:['weather'],
  components: {
    Temperature,
    FlexBreak,
    Humidity,
    VerticalDivider,
    Wind,
  },
};
</script>

<style>
.informer-container {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-wrap: wrap;
  width: 400px;
  min-height: 255px;
  padding: 30px;
  background-image: url("/img/forest.png");
  background-size: cover;
  background-position: center center;
  border-radius: 20px;
  box-shadow: 0px 0px 10px 0px rgba(50, 50, 50, 0.75);
}
</style>