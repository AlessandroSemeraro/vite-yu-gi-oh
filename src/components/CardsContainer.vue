<script>
import CardsElement from './CardsElement.vue';
import axios from 'axios';

export default{
   data(){
    return {
        cardsList :[],
        apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0'
    }
   },
   components : {
    CardsElement
   },
   methods : {
    getCards () {
        axios.get(this.apiUrl)
        .then((response) => {
            console.log (response);
            this.cardsList=response.data.data;
        })
    }
   },

   created(){
        this.getCards();
   }
}

</script>

<template >
<section class="container">
    <h2>
        Cards found: {{ cardsList.length }}
    </h2>
    <div class="container-cards">
        <CardsElement v-for="card in cardsList" :key="card.id" :card="card"/>
    </div>
</section>

</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
.container{
    background-color: white;
    

.container-cards{
    display: flex;
    flex-wrap: wrap;
    padding: 1rem;
}
    h2{
        background-color: $dark-bg;
        color: white;
        padding:1rem;
    }
}
    
</style>