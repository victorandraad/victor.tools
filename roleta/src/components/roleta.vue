<template>
  <div class="flex pt-20 justify-center ml-8">
    <img src="../assets/users.svg" alt="">
  </div>

  <div class="flex justify-center mt-4 gap-10">
    <div class="flex flex-col gap-2">
      <label>Number of Teams</label>
      <input type="number" v-model="teamCount" placeholder="Number of Teams" class="rounded-full h-7 text-center pl-3">
    </div>
    
    <label class="flex items-center space-x-3">
      <input type="checkbox" v-model="withAnimation" class="form-checkbox rounded text-indigo-600">
      <span>coming soon</span>
    </label>
  </div>

  <div class="flex flex-col gap-2 pt-10 justify-center mb-10">
    <div v-for="(player, index) in players" :key="index" class="flex gap-2 justify-center items-center">
      <svg @click="removePlayer(index)" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6 cursor-pointer">
        <path stroke-linecap="round" stroke-linejoin="round" d="m14.74 9-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 0 1-2.244 2.077H8.084a2.25 2.25 0 0 1-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 0 0-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 0 1 3.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 0 0-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 0 0-7.5 0" />
      </svg>
      <input type="text" v-model="player.name" :placeholder="'Player ' + (index + 1)" class="w-1/4 rounded-full h-7 text-center">
    </div>
    <svg @click="addPlayer" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6 cursor-pointer self-center ml-10">
        <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.75v14.5m7.25-7.25H4.75" />
    </svg>

    <input id="sort" type="button" value="Sortear" @click="handleShuffleAndLog" class="self-center ml- rounded-full w-1/4 text-center ml-8 bg-white text-black mt-4">
  </div>

  <div class="flex flex-wrap gap-10 justify-center hidden mb-10" id='team_bracket'>
    <div v-for="(team, index) in teams" :key="index" class="w-1/3">
      <div>
        <div class="ltr">
          <div class="bg-white text-black p-1 rounded-lg">Time: {{ index + 1 }}</div>
        </div>
        <div v-for="c in team" class="rounded-lg border-r-2 border-b-2 mb-1 mt-1">
          <div class="text-white p-1 rounded-lg"> {{ c.name }} </div>
        </div>
      </div>
    </div>
  </div>

  <div class="mt-4 hidden" id="logs">
    <h2 class="text-center text-xl mb-3">Log de Times</h2>
    <hr>
    <div class="flex gap-10 justify-center flex-wrap mt-3">
      <div v-for="(log, logIndex) in logs" :key="logIndex" class="mt-2 flex flex-col border-blue w-1/4 m-10">
        <h3 class="self-center bg-red-800 text-white w-full rounded-lg">Log {{ logIndex + 1 }}:</h3>
        <div class="flex justify-center">
          <div v-for="(team, index) in log" :key="index" class="border p-2 m-2 w-1/2">
            <h4 class="bg-white rounded text-black">Time {{ index + 1 }}:</h4>
            <ul>
              <li v-for="player in team" :key="player.name">{{ player.name }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const teamCount = ref(2)
const players = ref([{name: 'Victor'}, {name: 'Simon'}, {name: 'Roberto'}, {name: 'Theyloon'}])
const withAnimation = ref(false)

const shuffled = ref([])

const logs = ref([])

const teams = computed(() => {
  const playersPerTeam = Math.ceil(shuffled.value.length / teamCount.value)
  const teamsList = []

  for (let c = 0; c < teamCount.value; c++) {
    teamsList.push(shuffled.value.slice(c * playersPerTeam, (c + 1) * playersPerTeam))
  }

  return teamsList
})

const addPlayer = () => {
  players.value.push({ name: '' })
}

const removePlayer = (index) => {
  if (players.value.length > 4) {
    players.value.splice(index, 1)
  } else {
    players.value.splice(index, 1)
    players.value.push({ name: '' })
  }
}

const shufflePlayers = () => {
  const generateShuffle = () => {
    return players.value
      .map(player => ({ ...player }))
      .sort(() => Math.random() - 0.5);
  };

  const isUniqueShuffle = (shuffledPlayers) => {
    return !logs.value.some(loggedTeams => {
      const playersPerTeam = Math.ceil(shuffledPlayers.length / teamCount.value);
      const currentTeams = [];

      for (let c = 0; c < teamCount.value; c++) {
        currentTeams.push(shuffledPlayers.slice(c * playersPerTeam, (c + 1) * playersPerTeam));
      }

      return currentTeams.every((team, index) =>
        team.every(player => loggedTeams[index].some(loggedPlayer => loggedPlayer.name === player.name))
      );
    });
  };

  let shuffledPlayers;
  let attempts = 0;
  const maxAttempts = 100; // Limit the number of attempts to avoid infinite loops

  do {
    shuffledPlayers = generateShuffle();
    attempts++;

  } while (!isUniqueShuffle(shuffledPlayers) && attempts < maxAttempts);

  shuffled.value = shuffledPlayers;
  document.querySelector('#team_bracket').classList.remove('hidden');
  document.querySelector('#logs').classList.remove('hidden');
};

function logTeams() {
  logs.value.push(teams.value.map(team => team.slice()))
}

function handleShuffleAndLog() {
  shufflePlayers()
  logTeams()
}
</script>

<style scoped>
.size-6 {
  width: 1.5rem;
  height: 1.5rem;
}
.size-20 {
  width: 500px;
  height: 5rem;
}
</style>
