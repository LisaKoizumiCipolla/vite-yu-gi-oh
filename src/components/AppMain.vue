<template>
    <div class="main-section">
        <div class="wrapper">
            
            <DropdownMenu 
            @selectionEvent="selectArchetype"
            :dropdownList="archetypeList"
            />

            <div class="jumbo">
                <div class="card-header">
                    <h2>Found 39 cards</h2>
                </div>
                <div class="card-wrapper">
                    <div>
                        <CardList :cardList="cardList"/>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>
<script>
import CardList from './CardList.vue';
import axios from 'axios';
import DropdownMenu from './DropdownMenu.vue';

export default {

    data(){
        return{
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php",
            cardList : [],
            archetypeUrl :"https://db.ygoprodeck.com/api/v7/archetypes.php",
            archetypeList : []
        }
    },

    components : {
    CardList,
    DropdownMenu
},
    
    created(){
        axios.get(this.apiUrl, {
            params: {
                num : 20,
                offset : 750
            }
        })
        .then( (response) => {
            this.cardList = response.data.data;
            console.log(response.data);
        })
        .catch(function (error) {
            console.log(error);
        });

        
        axios.get(this.archetypeUrl)
        .then( (response) => {
            this.archetypeList = response.data.slice(60, 80);
            console.log(this.archetypeList);
        })
        .catch(function (error) {
            console.log(error);
        })
    },

    methods : {

        selectArchetype(archetype){

            console.log(archetype)
            axios.get(this.apiUrl, {
                params : {
                    num : 20,
                    offset : 0,
                    archetype : archetype
                }
            })

            .then( (response) => {
                this.cardList = response.data.data;
                console.log(response.data);
            })
            .catch(function (error) {
                console.log(error);
            });
            
        }
    }
    
}
</script>
<style lang="scss" scoped>
    .main-section{
        background-color: #D48F38;
        display: flex;
        margin: 0 auto;
    }

    .menu-button{
        padding: 30px 15px;
    }
    
    .jumbo{
        background-color: white;
        width: 100%;
        padding: 70px;
    }

    .card-wrapper{
        background-color: white;
        width: 100%;
    }

    .card-header{
        background-color: black;
        color: white;
        width: 100%;
    }

    h2{
        color: white;
        font-weight: 700;
        font-size: 1.3rem;
        padding: 30px 20px;
        margin: 0;
    }
</style>