<template>
    <div class="card-wrapper">
        <SingleCards v-for="card in cardList"
        :img = "card.card_images.image_url"
        :name = "card.name"
        :archetype = "card.archetype"
        />
    </div>
</template>

<script>
import SingleCards from './SingleCards.vue';
import axios from 'axios';

export default {

    data(){
        return{
            cardList : [],
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
        }
    },

    components : {
        SingleCards
    },

    created(){
        axios.get(this.apiUrl)
        .then( (response) => {
            this.cardList = response.data.data;
            console.log(response.data);
        })
        .catch(function (error) {
            console.log(error);
        })
    }
    
}
</script>

<style lang="scss">
    .card-wrapper{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        background-color: #D48F38;
    }
</style>