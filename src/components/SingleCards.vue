<template>
    <div class="card">
        <img :src="img" alt="">
        <h3>
            {{ name }}
        </h3>
        <h4>
            {{ archetype }}
        </h4>
    </div>
</template>

<script>
export default {
    props : {
        name : String,
        archetype : String,
        img : String,
    }
    
}
</script>

<style lang="scss">
    .card{
        width: calc((100% / 5) - 20px);
        height: 200px;
    }
</style>