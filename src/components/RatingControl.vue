<script setup>
import { ref } from 'vue'

defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])
// const activeOption = ref(props.modelValue)

const activate = (option) => {
  //   activeOption.value = option
  emit('update:modelValue', option)
}
</script>

<template>
  <ul>
    <li :class="{ active: modelValue === 'poor' }">
      <button @click="activate('poor')" type="button">Poor</button>
    </li>
    <li :class="{ active: modelValue === 'average' }">
      <button @click="activate('average')" type="button">Average</button>
    </li>
    <li :class="{ active: modelValue === 'great' }">
      <button @click="activate('great')" type="button">Great</button>
    </li>
  </ul>
</template>

<style scoped>
.active {
  border-color: #33035f;
}

.active button {
  color: #33035f;
}

ul {
  list-style-type: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>
