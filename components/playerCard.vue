<template>
    <div class="player-card-container">
    <div 
    v-for="player in playerData"
    :key="player.name"
    class="players-card"
    >
        <div class="players-img-container">
            <img src="/man.svg" alt="person"/>
            <h3>
                {{player.name}}
            </h3>
            </div>
            <div class="players-info">
                <strong>
                    Information
                </strong>
                <span>
                    Date Of Birth: {{player.DOB||"Not Available"}}
                </span>
                <span>
                    Bowling Style: {{player.Bowling_Skill||"Not Available"}}
                </span>
                <span>
                    Batting Style: {{player.Batting_Hand||"Not Availble"}}
                </span>
                <span>
                    Country: {{player.Country||"Not Available"}}
                </span>
            </div>
            <div class="button-container">
                <button class="player-button">
                     <a 
                        :href="`https://www.google.com/search?q=${player.name}`"
                        target="_blank"
                        rel="noopener noreferrer"
                     >
                        More Info
                    </a>                    
                </button>
            </div>
        </div>
  </div>
</template>
<script>
export default {
    name:"PlayerCard",
    props:['playerData']
}
</script>
<style>
    .player-card-container{
    padding: 1rem;
    display: flex;
    width: 100%;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: flex-start;
    align-items: center;
    align-content: center;
    margin: auto;
}

.player-card{
    width: 25rem;
    height: 13rem;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    background-color: coral;
    border-radius: 7px;
    margin: 0.5rem;
    padding: 0.5rem;
}

.player-img-container{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 0.5rem;
}

.player-card img{
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background-color: cadetblue;
}

.player-info{
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    color: #ffffff;
}

.players-card{
    width: 25rem;
    height: 12rem;
    border-radius: 7px;
    margin: 0.5rem;
    padding: 1rem;
    display: grid;
    grid-template-rows: 35% 40% 23%;
    color: #fff;
    background: #599425;
}

.players-img-container{
    display: flex;
    flex-direction: row;
}

.players-img-container img{
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin-right: 1rem;
    background-color: cadetblue;
}

.players-info{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
}

.players-info span{
    font-size: 0.8rem;
}

.players-card strong{
    font-style: italic;
}

h3{
    text-align: center;
}

.button-container{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
}

.player-button{
    background-color: transparent;
    border-color: black;
    font-weight:bold;
    outline: none;
    text-decoration: none;
    border-radius: 7px;
    padding: 0.2rem 1.2rem;
    border-style: solid;
    font-size: small;
    color: #fff;
}

.player-button:hover{
    background-color: grey;
}

a{
    text-decoration: none;
    color: #fff;
}
</style>
