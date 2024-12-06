<template>
    <div class="">
        <div class="sm:hidden">
          <label for="tabs" class="sr-only">Select a tab</label>
        </div>
        <div class="hidden mt-8 overflow-hidden bg-white shadow sm:block sm:rounded-md">
          <div class="border-b border-gray-200">
            <nav class="flex -mb-px" aria-label="Tabs">
              <button
                @click="currentTab(1)"
                :class="[tab == 1 ? 'border-indigo-500 text-indigo-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300', 'w-1/4 py-4 px-1 text-center border-b-2 font-medium text-sm']"
              >
                Oitavas de Final
              </button>
            
              <button
                @click="currentTab(2)"
                :class="[tab == 2 ? 'border-indigo-500 text-indigo-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300', 'w-1/4 py-4 px-1 text-center border-b-2 font-medium text-sm']"
             
              >
                Quartas de Final
              </button>
          
            
              <button
                @click="currentTab(3)"
                :class="[tab == 3 ? 'border-indigo-500 text-indigo-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300', 'w-1/4 py-4 px-1 text-center border-b-2 font-medium text-sm']"
               
              >
                Semi-final
              </button>
  
              <button
                @click="currentTab(4)"
                :class="[tab == 4 ? 'border-indigo-500 text-indigo-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300', 'w-1/4 py-4 px-1 text-center border-b-2 font-medium text-sm']"
              >
                Final
              </button>
            </nav>
          </div>
        </div>
      </div>
      <div>
        <div class="container mx-auto">
          <div class="p-3 mt-2">
            <div v-if="tab === 1">
              <Oitavas />
            </div>
            <div v-if="tab === 2">
              <Quartas/>
            </div>
            <div v-if="tab === 3">
              <SemiFinal />
            </div>
            <div v-if="tab === 4">
              <Final/>
            </div>
          </div>
        </div>
      </div>
  </template>
  <script>
import Oitavas from '../Brackets/Oitavas.vue';
import Quartas from '../Brackets/Quartas.vue';
import SemiFinal from '../Brackets/SemiFinal.vue';
import Final from '../Brackets/Final.vue';
  export default {
    components:{
      Oitavas,Quartas,SemiFinal,Final 
    },
    data() {
      return {
        tab: 1
      };
    },
    methods: {
      currentTab: function (tabNumber) {
        this.tab = tabNumber;
      },
    },

  };
  </script>