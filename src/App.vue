<template>
  <div>
    <Beverage
      :isIced="currentTemp === 'Cold'"
      :creamer="currentCreamer"
      :syrup="currentSyrup"
      :beverage="baseBev"
    />
    <Selection
      category="Temperature"
      :items="temps"
      :current="currentTemp"
      @update:modelValue="currentTemp = $event"
    />
    <Selection
      category="Creamer"
      :items="creamers"
      :current="currentCreamer"
      @update:modelValue="currentCreamer = $event"
    />
    <Selection
      category="Syrup"
      :items="syrups"
      :current="currentSyrup"
      @update:modelValue="currentSyrup = $event"
    />
    <Selection
      category="Base"
      :items="bases"
      :current="baseBev"
      @update:modelValue="baseBev = $event"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import Selection from "./components/Selection.vue";
// Define reactive data
const temps = ["Hot", "Cold"];
const creamers = ["None", "Milk", "Cream", "Half & Half"];
const syrups = ["None", "Vanilla", "Caramel", "Hazelnut"];
const bases = ["Coffee", "Green Tea", "Black Tea"];
const currentTemp = ref("Hot");
const currentCreamer = ref("None");
const currentSyrup = ref("None");
const baseBev = ref("Coffee");
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>