<template>
  <div id=app>
    <!-- calling matchupTitle.vue an passing in the objects of team1
    and team2 -->
    <matchup-title :team1="team1" :team2="team2"></matchup-title>
    <game-status :team1="team1" :team2="team2"></game-status>
    <div class="scores">
      <score-card :score="team1.score" @pointAdded="updateTeamScore(team1, 1)" @pointSubtracted="updateTeamScore(team1, -1)"></score-card>
      <score-card :score="team2.score" @pointAdded="updateTeamScore(team2, 1)" @pointSubtracted="updateTeamScore(team2, -1)"></score-card>
    </div>
  </div>
</template>

<script>
import MatchupTitle from './components/MatchupTitle.vue';
import ScoreCard from './components/ScoreCard';
import GameStatus from './components/GameStatus';


export default {
  components: { MatchupTitle, ScoreCard, GameStatus },

  data() {
    return {
      team1: {
        name: "Team 1",
        score: 0
      },
      team2: {
        name: "Team 2",
        score: 0
      }
    }
  },
  methods: {
    updateTeamScore(team, points) {
      const updated = team.score + points;
      if (updated >= 0) {
        team.score = updated;
      } 
    }
  }

};
</script>

<style>
body {
  background-color: #2c3e50;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgba(255, 255, 255, 0.8);
  margin-top: 60px;
}
.scores {
  display: flex;
  justify-content: space-evenly;
}

</style>