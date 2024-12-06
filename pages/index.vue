<template>
  <NavBar />
  <div class="p-8">
    <h1 class="text-3xl font-bold mb-6">COPA BOMBA PATCH</h1>
    <button @click="modalOpen = true" class="bg-blue-600 text-white px-4 py-2 rounded-md mb-4">
      <PlusIcon class="w-5 h-5 inline-block mr-2" /> Adicionar Time
    </button>
    <TeamAdd :isOpen="modalOpen" @update:isOpen="modalOpen = $event" @save="addTeam" />
    <div class="grid grid-cols-1 gap-5 sm:grid-cols-2 sm:gap-6 lg:grid-cols-4">
      <TeamCard v-for="team in teams" :key="team.id" :teamLogo="team.logo" :teamName="team.name"
        :managerName="team.manager" />
    </div>
    <TournamentBracket />
  </div>
</template>

<script >
import { PlusIcon } from '@heroicons/vue/24/outline'
import TeamCard from '~/components/home/TeamCard.vue'
import TeamAdd from '~/components/home/TeamAdd'
import TournamentBracket from '~/components/home/TournamentBracket.vue';
import NavBar from '@/components/home/NavBar.vue'
export default {
    components: {
    TeamCard,TeamAdd ,TournamentBracket,NavBar,
    PlusIcon ,
  },
  setup() {
        const teams = [
            {  name: 'Barcelona', href: '#', manager: 'H', logo: '/default-logo.png'},
            {  name: 'Corinthians', href: '#', manager: 'T', logo: '/default-logo.png' },
           
        ]
        const modalOpen= ref(false)

        return {
            teams, modalOpen
        }
    },
    methods: {
    addTeam(team) {
      this.teams.push({
        id: this.teams.length + 1,
        ...team,
        logo: '/default-logo.png',
        href:'#'
      });
    },
  },
}
</script>
