<script>
import CardsElement from './CardsElement.vue';
import axios from 'axios';
import { store } from '../js/store';

export default{
   data(){
    return {
        store
    }
   },
   components: {
    CardsElement

   },
   methods: {
    
   },
   

   created(){
        this.store.getCards();
   }
}

</script>

<template >
<section class="container">
    <h2>
        Cards found: {{ store.cardsList.length }}
    </h2>
    <div class="container-cards">
        <CardsElement v-for="card in store.cardsList" :key="card.id" :card="card"/>
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