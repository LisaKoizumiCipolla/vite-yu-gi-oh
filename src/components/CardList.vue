<template>
    <div>
        <SingleCards v-for="card in CardList"
        :img = "card.image_url"
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
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
        }
    },

    components : {
        SingleCards
    },

    created(){
        axios.get(this.apiUrl)
        .then( (response) => {
            console.log(response.data.results);
        })
        .catch(function (error) {
            console.log(error);
        })
    }
    
}
</script>

<style lang="scss">
    
</style>