<script>
import CardsContainer from './CardsContainer.vue';
export default {
    components: {
        CardsContainer,
    },
}
</script>

<template >
    <main>
        <CardsContainer />
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

main {
    background-color: $bg-yu-gi-oh;
    display: flex;
    justify-content: center;
    padding: 4rem ,
}
</style>