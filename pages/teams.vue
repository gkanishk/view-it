<template>
  <div class="container">
      <input v-model="searchData" v-on:input="showOutput" placeholder="Search Data  🔎"/>
      <div v-if="searchData!==''" style="width:100%" class="search-container">
          <h2>
              Search Result
          </h2>
          <TeamCard :teamsData="searchTeamData"></TeamCard>
          <div v-if="!searchTeamData.length">
              No data found.
          </div>
      </div>
      <TeamCard :teamsData="teams"></TeamCard>
  </div>
</template>

<script>
import teams from '../assets/team.json'
import teamCard from '../components/teamCard.vue'
export default {
  components: { teamCard },
    data(){
        return {
            teams: teams,
            searchData: "",
            searchTeamData: null
        }
    },
    methods:{
        showOutput:function (){
            if(this.searchData==""){
                this.searchTeamData=null;
                return;
            }
            this.searchTeamData=this.teams.filter(teamData=>{
            if(teamData.name.toUpperCase().includes(this.searchData.toUpperCase()))
            return teamData;
        })
        console.log(this.searchTeamData)
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

    .search-container{
        width: 100%;
        text-align: center;
    }
</style>
