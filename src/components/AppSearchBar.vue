<script>
import axios from 'axios';
export default {
    data() {
        return {
            archetypesList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php'
        }
    },
    methods: {
        getArchetypes() {
            axios.get(this.apiUrl)
                .then((response) => {
                    console.log(response);
                    this.archetypesList = response.data;
                })
        }
    },

    created() {
        this.getArchetypes();
    }
}

</script>
<template>
    <section class="container-select">
        <select class="mySelect">
            <option value="1"></option>
            <option v-for="(archetype, index) in archetypesList" :key="index" :value="archetype.archetype_name"> {{ archetype.archetype_name }}</option>
            <option value="3"></option>
        </select>
    </section>
</template>

<style lang="scss" scoped>
.container-select {
    display: flex;
    justify-content: center;

    .mySelect {
        width: 100%;
        padding: 0.5rem;
        margin-bottom: 2rem;

    }
}
</style>