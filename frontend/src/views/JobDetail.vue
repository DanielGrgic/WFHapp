<template>
    <div v-if="job" class="JobDetail">
        
        <proba :proba="job"   />
    </div>
</template>

<script>

import proba from '@/components/proba.vue';
import {Posts} from '@/services';

export default {
    props: ['id'],
    data() {
        return {
            job: {
              id: "5eb400586bceea42ac98ebf5",
              ime:"Marko",
              prezime:"Markić",
              opis_posla:"I need the autocad expert for my job. Details will be shared.",
              kategorija_posla:"Engineering and science",
              naziv_posla:"AutoCAD expert",
              potrebne_vjestine:"CAD/CAM, Solidworks, AutoCAD, Drafting, Building architecture...",
              zarada:"50$",
              posted_at:1588854872335
             }
        };
    },
    //async mounted() {
    //    console.log(this.id);
        //upit na backend
    //    this.job = await Posts.getOne(this.id);
    //    console.log(this.job)
    //},

    name: 'Job-Detail',
    components: {
        
        proba
    }
};
</script>

<style scoped>
button {
    margin-bottom: 20px;
}
.JobDetail{
    width: 100%;
}
</style>
