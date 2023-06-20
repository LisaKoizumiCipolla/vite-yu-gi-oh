<template>
    <div class="card" id="background">
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

<style lang="scss" scoped>
    .card{
        width: calc((100% / 5) - 20px);
        margin-bottom: 20px;

        h3{
            color: white;
            font-weight: 700;
            padding: 25px;
        }

        h4{
            color: black;
            
        }
    }

    #background {
        background-color: #D48F38;
    }
</style>