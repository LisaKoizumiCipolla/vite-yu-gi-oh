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
                <div class="card-wrapper">
                    <div class="card-header">
                        <h2>Found 39 cards</h2>
                    </div>
                    <div>
                        <CardList />
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>
<script>
import CardList from './CardList.vue'

export default {
    components : {
        CardList
    }
    
}
</script>
<style lang="scss" scoped>
    .main-section{
        background-color: #D48F38;
        height: 1000px;
        display: flex;
        margin: 0 auto;
    }

    .dropdown{
        padding: 30px 15px;
    }
    
    .jumbo{
        background-color: white;
        width: 100%;
        height: 800px;
    }

    .card-wrapper{
        background-color: white;
        width: 100%;
        padding: 65px;
    }

    .card-header{
        background-color: black;
        color: white;
    }

    h2{
        color: white;
        font-weight: 700;
        font-size: 1.3rem;
        padding: 30px 20px;
    }
</style>