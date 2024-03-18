<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
    </ul>
  </div>
  <div>
    <Syrup :Syrups="selectedSyrup" />
    <div>
      <template v-for="temp in syrups" :key="temp">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${temp}`"
              :value="temp"
              v-model="selectedSyrup"
            />
            {{ temp }}
          </label>
        </template>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import Syrup from "./components/Syrup.vue";
// Define reactive data
const temps = ref(["Hot", "Cold"]);
const currentTemp = ref("Hot");
const syrups = ref(["Vanilla", "Caramel", "Hazelnut"])
const selectedSyrup = ref("Vanilla");
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
