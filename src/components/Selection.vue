<template>
    <div>
      <ul>
        <li>
          {{ category }} :
          <template v-for="item in items" :key="item">
            <label>
              <input
                type="radio"
                :name="category"
                :id="`r${item}`"
                :value="item"
                :modelValue="current"
                v-on:click="emit('update:modelValue', item)"
              />
              {{ item }}
            </label>
          </template>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup lang="ts">
  const props = defineProps(["items", "current", "category"]);
  const emit = defineEmits(["update:modelValue"]);
  </script>