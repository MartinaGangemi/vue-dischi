<template>
   <div>
        <select class="form-select" aria-label="Default select example" @submit.prevent="$emit('clicca')" :value="genereMusicale" 
            @input="$emit('input', $event.target.value)"
            @click="$emit('clicca', genereMusicale)">
            <option  value="">Seleziona il genere musicale</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        
    
   </div>
</template>

<script>

export  default{
    name:"SelectComponent",
}
</script>
