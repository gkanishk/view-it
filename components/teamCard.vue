<template>
<div class="card-container">
    <div 
            class="team-card"
            v-for="teamData in teamsData"
            :key="teamData.name"
            >
            <img src="/logo.jpg" alt="logo ipl"/>
            <h3>{{teamData.name}}</h3>
            <button class="button-main">
                <a
                rel="noopener noreferrer"
                :href="`https://www.google.com/search?q=${teamData.name}`" 
                target="_blank"
                >
                More Info
                </a>                    
            </button>
        </div>
</div>
</template>

<script>
export default {
    name:'TeamCard',
    props: ['teamsData']
}
</script>
<style>
    .card-container{
        padding: 1rem;
        display: flex;
        width: 95%;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: flex-start;
        align-items: center;
        align-content: center;
        margin: auto;
    }
    .team-card{
    width: 17rem;
    height: 20rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 5px;
    color: #ffffff;
    margin: 1rem;
    background-color: #599425;
}

.team-card img{
    width: 120px;
    height: 120px;
    border-radius: 50%;
}

.button-main{
    background-color: transparent;
    border-color: black;
    font-weight:bold;
    outline: none;
    text-decoration: none;
    border-radius: 7px;
    padding: 0.5rem 1.2rem;
    border-style: solid;
    font-size: small;
    margin: 1rem 0;
}

.button-main:hover,
.button-main:active,
.button-main:focus{
    background-color: #48d1c4;
}

@media (max-width:660px){
    .card-container{
        width: 100%;
      }
      .team-card{
        margin: 1rem auto;
      }
}
</style>