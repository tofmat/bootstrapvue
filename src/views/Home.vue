<template>
    <b-container class="bv-example-row">
      <b-row align-v="center">
        <JobCard v-for="job in displayJobs" :key="job.id" :name="job.name"/>
      </b-row>
      <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      first-text="First"
      prev-text="Prev"
      next-text="Next"
      last-text="Last"
      @input="paginate(currentPage)"
    ></b-pagination>
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
  data(){
    return{
       jobs: [],
       displayJobs: [],
       currentPage: 1,
       rows: 1,
       perPage: 3
    }
  }, 
  mounted(){
    this.fetchData();
  },
  methods: {
    async fetchData(){
      this.$store.dispatch("fetchJobs")
      console.log(this.$store.getters.jobs);
      const res = await fetch("jobs.json");
      const val = await res.json();
      this.jobs = val;
      this.displayJobs = val.slice(0, 3);
      this.rows = this.jobs.length;
      console.log(val);
    },
    paginate(currentPage){
      const start = (currentPage - 1) * this.perPage;
      this.displayJobs = this.jobs.slice(start, start+3)
    }
  }
};
</script>
