<template>
    <b-container class="bv-example-row">
      <b-row align-v="center">
        <JobCard />
        <JobCard />
        <JobCard />
      </b-row>
    </b-container>
</template>

<script>
// @ is an alias to /src
import JobCard from '../components/JobCard'
export default {
  name: "Home",
  components: {
    JobCard
  },
  mounted(){
    this.fetchData();
  },
  methods: {
    async fetchData(){
      const res = await fetch 
    }
  }
};
</script>
