<template>
    <div>
        <div class="row row-cols-5 g-4 mt-4" v-if = "loading === false ">
            <Cd :cd = "cd" v-for=" (cd, index) in cdList" :key="index" />
        </div>
        <div class="pt-5 row justify-content-center" v-else>
            <div class="loader"></div>
            <h2 class="text-white text-center pt-3">...Loading</h2>
        </div>
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
        link :"https://flynn.boolean.careers/exercises/api/array/music",
        cdList: null,
        loading: true,
        error: null,
        };
    },

    methods:{
        callApi(){
            axios.get(this.link)
            .then((response) =>{
                this.cdList = response.data.response;
                this.loading = false;
            })
        }
    },

    mounted() {
    this.callApi();
    },
})
</script>

<style lang="scss" scoped>

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

