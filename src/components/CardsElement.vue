<script>
export default {
    props: {
        card: {
            type: Object,
            required: true,
        }
    }
}
</script>
<template>
    <div class="card-container">
        <img :src="card.card_images[0].image_url" alt="card-image">
        <h3>{{ card.name }}</h3>
        <h5>{{ card.archetype }}</h5>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.card-container {
    background-color: $bg-yu-gi-oh;
    width: calc(100% / 5 - 1rem);
    margin: 0.5rem;
    text-align: center;

    img{
        width: 100%;
    }

    h3{
        color: white;
        text-transform: uppercase;
        font-size: 1rem;
    }

    h5{
        margin-top: 0.5rem;
    }
    
}
</style>