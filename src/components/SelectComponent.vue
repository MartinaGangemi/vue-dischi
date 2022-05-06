<template>
    <select class="form-select" aria-label="Default select example" @submit.prevent="$emit('clicca')" :value="genereMusicale" 
    @input="$emit('input', $event.target.value)"
    @click="$emit('clicca', genereMusicale)">
        <option selected>Seleziona  il genere</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>
</template>

<script>

export  default{
    name:"SelectComponent",
}
</script>
