<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <div class="options">
      <label>Temperature:</label>
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
    </div>

    <!-- Creamer options -->
    <div class="options">
      <label>Creamer:</label>
      <template v-for="creamer in creamers" :key="creamer">
        <label>
          <input
            type="radio"
            name="creamer"
            :id="`r${creamer}`"
            :value="creamer"
            v-model="selectedCreamer"
          />
          {{ creamer }}
        </label>
      </template>
    </div>

    <!-- Syrup options -->
    <div class="options">
      <label>Syrup:</label>
      <template v-for="syrup in syrups" :key="syrup">
        <label>
          <input
            type="radio"
            name="syrup"
            :id="`r${syrup}`"
            :value="syrup"
            v-model="selectedSyrup"
          />
          {{ syrup }}
        </label>
      </template>
    </div>

    <!-- Base beverage options -->
    <div class="options">
      <label>Base Beverage:</label>
      <template v-for="base in baseBeverages" :key="base">
        <label>
          <input
            type="radio"
            name="base"
            :id="`r${base}`"
            :value="base"
            v-model="selectedBase"
          />
          {{ base }}
        </label>
      </template>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";

// Define reactive data
const temps = ref(["Hot", "Cold"]);
const currentTemp = ref("Hot");

// Creamer options
const creamers = ref(["None", "Milk", "Cream", "Half & Half"]);
const selectedCreamer = ref("None");

// Syrup options
const syrups = ref(["None", "Vanilla", "Caramel", "Hazelnut"]);
const selectedSyrup = ref("None");

// Base beverage options
const baseBeverages = ref(["Coffee", "Green Tea", "Black Tea"]);
const selectedBase = ref("Coffee");
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
.options {
  margin-bottom: 1rem;
}
</style>