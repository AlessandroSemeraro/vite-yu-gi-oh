<script>
import CardsContainer from './CardsContainer.vue';
import AppSearchBar from './AppSearchBar.vue';
export default {
    components: {
        CardsContainer,
        AppSearchBar,
    },
}
</script>

<template >
    
    <main>
        
        <section class="container-cards">
            <AppSearchBar />
            <CardsContainer />
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;



.container-cards{
    background-color: $bg-yu-gi-oh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 
}
</style>