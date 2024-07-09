<script>
import AppHeader from './components/AppHeader.vue'
import CharacterList from './components/CharacterList.vue';

// axios import 

import axios from 'axios';

// store import 

import { store } from './store';

export default {
    name: 'App',
    data(){
        return {
            store,
        }
    },  
    methods: {
        getCharacters(){
            axios.
            get(store.apiUrl)
            .then(res => {
                console.log(res.data.results);
                store.characterList = res.data.results;
            }).catch(err => {
                console.log(err);
            });
        }
    },
    created() {
        this.getCharacters();
    },
    components: {
        AppHeader,
        CharacterList,
    }
}
</script>

<template>
    <AppHeader message="Rick & Morty" />
    <main>
        <CharacterList />
    </main>
</template>

<style lang="scss">
@use './style/general.scss';

main {
    padding-top: 20px;
}

</style>
