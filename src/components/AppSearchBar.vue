<script>
import axios from 'axios';
import {store} from '../js/store'
export default {
    data() {
        return {
            archetypesList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php',
            store,
            selectedArchetype:'',
        }
    },
    methods: {
        getArchetypes() {
            axios.get(this.apiUrl)
                .then((response) => {
                    
                    this.archetypesList = response.data;
                })
        },
        selectArchetype(archetype){
            console.log(archetype)
            this.store.getCards(archetype);
        }
    },

    created() {
        this.getArchetypes();
    }
}

</script>
<template>
    <section class="container-select">
        <select class="mySelect" @change="selectArchetype(selectedArchetype)" v-model="selectedArchetype">
            <option value="">Select filter</option>
            <option v-for="(archetype, index) in archetypesList" :key="index" :value="archetype.archetype_name" > {{ archetype.archetype_name }}</option>
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