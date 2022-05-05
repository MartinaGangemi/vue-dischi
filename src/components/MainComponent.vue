<template>
    <div>
        sono il main
        <CdList />
    </div>
    
</template>

<script>
import CdList from "@/components/CdListComponent.vue"
export default ({
    name:"MainComponent",
    components:{
        CdList,
    }
})
</script>