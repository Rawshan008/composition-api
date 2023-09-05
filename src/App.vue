<template>
  <h1>{{ heading }} </h1>
  <div>
    <input v-model="heading" type="text">
  </div>

  <div>
    <h1>{{ counterObj.title }}</h1>
    <button @click="handleDecrease">Desrease</button>
    <h1>{{ counterObj.count }}</h1>
    <button @click="handleIncrease">Increase</button>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue';

  const heading = ref('This is title');

  const counterObj = reactive({
    count: 0,
    title: "Counter Title "
  });

  const handleDecrease = ()  => {
    counterObj.count--;
  }

  const handleIncrease = () => {
    counterObj.count++;
  }
</script>