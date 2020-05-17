<template>
  <div class="pozadina">
      <div class="naslov">
          <div @click="gotoDetails(job)" :key="job.id" v-for="job in jobs">
            <OneJob :info="job" />
          </div>   
      </div>
    
  </div>    
</template>

<script>
import _ from 'lodash';
import { Posts } from '@/services';
import OneJob from '@/components/OneJob.vue';
import proba from '@/components/proba.vue';


export default {
  data() {
        return {
           jobs: [
             {
              id: "5eb400586bceea42ac98ebf5",
              ime:"Marko",
              prezime:"Markić",
              opis_posla:"I need the autocad expert for my job. Details will be shared.",
              kategorija_posla:"Engineering and science",
              naziv_posla:"AutoCAD expert",
              potrebne_vjestine:"CAD/CAM, Solidworks, AutoCAD, Drafting, Building architecture...",
              zarada:"50$",
              posted_at:1588854872335
             },
             {
              id: "5eb401a33cc232358ca86c94",
              ime:"Ivan",
              prezime:"Ivanić",
              opis_posla:"I need the HTML expert for my job. Details will be shared.",
              kategorija_posla:"WEB designing",
              naziv_posla:"HTML expert",
              potrebne_vjestine:"HTML, CSS, PHP, WEB DESIGNING",
              zarada:"100$",
              posted_at:1588854871335
             }
            ],
            

        };
    },
    //watch: {
    //    'store.searchTerm': _.debounce(function(val) {
    //        this.fetchPosts(val);
    //    }, 500)
    //},
   // created() {
    //    this.GetAllJobs();
        
    //},
    name: 'Jobs',
    methods: {
        //async GetAllJobs() {

        //    this.jobs = await Posts.getAll();
          //  console.log(this.jobs)

        //},
        gotoDetails(job) {
            this.$router.push({ path: `Job/${job.id}` });
        }
        //gotoDetails(card) {
        //    this.$router.push({ path: `post/${card.id}` });
        //}
    },
    components: {
        OneJob,
        proba
    }
  
}
</script>

<style scoped>
.pozadina{
    background-color:white;
    width: 70%;
    margin: 5% auto;
    
  }

  .naslov{
    
    width: 90%;
    text-align: left;
    margin: auto;
    margin-bottom: 5%;
    padding: 2% 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    background-color:white;
  }
  

</style>  