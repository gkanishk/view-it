<template>
  <div class="container">
      <input v-model="searchData" v-on:input="showOutput" placeholder="Search Data  🔎"/>
      <div v-if="searchData!==''" style="width:100%" class="search-container">
          <h2>
              Search Result
          </h2>
          <player-card :playerData="searchPlayerData"></player-card>
          <div v-if="!searchPlayerData.length">
              No data found.
          </div>
      </div>
      <player-card :playerData="playerData"></player-card>
  </div>
</template>

<script>
import playerList from '../assets/players.json'
import playerCard from '../components/playerCard.vue'
export default {
  components: { playerCard },
    data(){
        return {
            playerData:playerList,
            searchData: "",
            searchPlayerData: null
        }
    },
    methods:{
        showOutput:function (){
            if(this.searchData==""){
                this.searchPlayerData=null;
                return;
            }
            this.searchPlayerData=this.playerData.filter(playerData=>{
            if(playerData.name.toUpperCase().includes(this.searchData.toUpperCase()))
            return playerData;
        })
        }
    }
}
</script>

<style>
.container{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 2rem;
    }
</style>
