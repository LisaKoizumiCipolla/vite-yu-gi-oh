<template>
    <div class="card-wrapper">
        <SingleCards v-for="card in cardList"
        :img = "card.card_images.length > 0 ? card.card_images[0].image_url : ''"
        :name = "card.name"
        :archetype = "card.archetype"
        />
    </div>
</template>

<script>
import SingleCards from './SingleCards.vue';

export default {

    data(){
        return{
        }
    },

    components : {
        SingleCards
    },

    props : {
        cardList : Array
    }

    
    
}
</script>

<style lang="scss">
    .card-wrapper{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        background-color: #D48F38;
        text-align: center;
    }
</style>