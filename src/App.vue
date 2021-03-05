<template>
  <div id=app>
    <!-- calling matchupTitle.vue an passing in the objects of team1
    and team2 -->
    <matchup-title :team1="team1" :team2="team2"></matchup-title>
    <score-card :score="team1.score"></score-card>
    <score-card :score="team2.score"></score-card>
  </div>
</template>

<script>
import MatchupTitle from './components/MatchupTitle.vue';
import ScoreCard from './components/ScoreCard';

export default {
  components: { MatchupTitle, ScoreCard },

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

    };
  },

}
</script>

<style>

</style>