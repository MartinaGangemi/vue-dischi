<template>
    <header>
        <!-- logo -->
        <div class="logo_img">
            <img src="@/assets/img/logo.png" alt="">
        </div>
    </header>
</template>

<script>
export default ({
    name:"HeaderComponent",
    
})
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
