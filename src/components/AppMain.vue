<template>
    <div class="main-section">
        <div class="wrapper">
            
            <div class="dropdown">
                <button class="btn btn-light dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                    Alien
                </button>
                <ul class="dropdown-menu">
                    <li><button class="dropdown-item" type="button">Alien</button></li>
                    <li><button class="dropdown-item" type="button">Another action</button></li>
                    <li><button class="dropdown-item" type="button">Something else here</button></li>
                </ul>
            </div>

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
import axios from 'axios'

export default {

    data(){
        return{
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
            cardList : []
        }
    },

    components : {
        CardList
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
<style lang="scss" scoped>
    .main-section{
        background-color: #D48F38;
        display: flex;
        margin: 0 auto;
    }

    .dropdown{
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