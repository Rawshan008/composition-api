<template>
  <h1>Employee Present: {{ employeePresent }}</h1>
  <h2>Full Name: {{ fullName }}</h2>

</template>

<script setup>
import { computed, reactive } from 'vue';

  const employee = reactive({
    books: [
      'book 1',
      'book 2',
      'book 3'
    ]
  });

  const empoyeeName = reactive({
    firstName: 'Rawshan',
    lastName: 'Ali'
  });

  const employeePresent = computed(() => {
    return employee.books.length > 0 ? 'Yes' : 'No';
  });

  const fullName = computed({
    get(){
      return empoyeeName.firstName+ ' ' + empoyeeName.lastName;
    },

    set(newName) {
      [empoyeeName.firstName, empoyeeName.lastName] = newName.split(' ');
    }
  })


</script>