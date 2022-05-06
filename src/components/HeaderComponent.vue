<template>
    <header class="row align-items-center">
        <!-- logo -->
        <div class="col logo_img">
            <img src="@/assets/img/logo.png" alt="">
        </div>
        <!-- form-select -->
        <div class="col">
            <Select v-model="genereMusicale" @clicca="search" />
        </div>
    </header>
</template>

<script>
import Select from "@/components/SelectComponent.vue";
import state from "@/state.js";
export default {
    name:"HeaderComponent",
    components:{
        Select,
    },

    data() {
        return {
        genereMusicale: "",
        };
    },

    methods: {
    search() {
      console.log('pincopallo ...');
      state.genereMusicale = this.genereMusicale;
      console.log(state.genereMusicale);
    },
  },

};
</script>

<style lang="scss" scoped>
    header{
        background-color: $primary;
        padding: 1rem;
    }

    .logo_img{
        height: 50px;
    }
   
</style>
