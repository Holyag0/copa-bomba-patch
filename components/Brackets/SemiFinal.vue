<template>
    <div class="p-8">
      <h1 class="text-3xl font-bold mb-6">Chaveamento Oitavas de Final</h1>
      <div class="grid grid-cols-4 gap-4">
        <div v-for="match in matches" :key="match.id" class="bg-white rounded-lg shadow-md p-4">
          <div class="flex justify-between items-center mb-4">
            <span class="font-bold">{{ match.team1 }}</span>
            <span>{{ match.date }}</span>
            <span class="font-bold">{{ match.team2 }}</span>
          </div>
          <div class="flex justify-between items-center">
            <img :src="match.flag1" alt="Flag 1" class="w-6 h-6">
            <img :src="match.flag2" alt="Flag 2" class="w-6 h-6">
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        matches: [
          { id: 1, team1: 'Deportivo Cuenca', flag1: '/path-to-ecuador-flag.png', team2: 'Fluminense', flag2: '/path-to-brazil-flag.png',date: 'x' },
          { id: 2, team1: 'San Lorenzo', flag1: '/path-to-argentina-flag.png', team2: 'Nacional', flag2: '/path-to-uruguay-flag.png', date: 'x' },
        ]
      }
    }
  }
  </script>