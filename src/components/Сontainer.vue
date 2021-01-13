<template>
  <div class="informer-container">
    <Temperature />
    <FlexBreak />
    <Humidity />
  </div>
</template>

<script>
import Temperature from "./Temperature.vue";
import FlexBreak from "./FlexBreak.vue";
import Humidity from "./Humidity.vue";
export default {
  name: "Container",
  components: {
    Temperature,
    FlexBreak,
    Humidity,
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