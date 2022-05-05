<template>
    <div>
        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 g-4 mt-4" v-if = "!loading === true ">
            <Cd :cd = "cd" v-for=" (cd, index) in cdList" :key="index" />
        </div>
        <div class="d-flex  justify-content-center align-items-center bg" v-if="!error===false && !loading === true">
            <h2 class="text-white">  {{error}} </h2>
        </div>
        <div class=" d-flex flex-column justify-content-center align-items-center bg" v-else>
            <div class="loader"></div>
            <h2 class="text-white text-center pt-3">...Loading</h2>
        </div>
        <!-- se il collegamento con axios non funziona -->
        

    </div>
    
</template>

<script>
import axios from "axios"
import Cd from '@/components/CdComponent.vue'

export default ({
    name:"CdListComponent",
    components:{
        Cd
    },

    data (){
        return {
        link :"https://flynn.boolean.careers/exercises/api/array/musi",
        cdList: null,
        loading: true,
        error: false,
        };
    },

    methods:{
        timer(){
            setTimeout(()=>{
                this.loading = false
            }, 2000);
        },

        callApi(){
            axios.get(this.link)
            .then((response) =>{
                this.cdList = response.data.response;
            })
            .catch((error) => {
                this.error = ` ${error}`;
            });
        }
    },

    mounted() {
    this.callApi();
    this.timer();
    },
})
</script>

<style lang="scss" scoped>
    .bg{
        height: calc(100vh - 82px),
    }

    .loader {
    border: 10px solid $light;
    border-radius: 50%;
    border-top: 10px solid $white;
    width: 80px;
    height: 80px;
    animation: spin 2s linear infinite; 
    }

    @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
    }

</style>

