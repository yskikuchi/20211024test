<template>
  <div class="about">
    <h2>current team:{{teamName}}</h2>
    <button @click="increaseNum">counter</button>
    <h3>{{$store.state.sum}}</h3>
    <p>Last team name clicked:{{$store.state.lastTeam}}</p>
    <router-link to="/">戻る</router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      teamName:this.$route.query.teamName,
    };
  },
  methods:{
    increaseNum(){
      this.$store.commit('countUp', this.teamName);
    }
  }
};
</script>