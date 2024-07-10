<script>
import AppHeader from './components/AppHeader.vue';
import SelectRace from './components/SelectRace.vue';
import CardList from './components/CardList.vue';

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
        getCard(){
            let endPoint = store.apiUrl;

            if (store.search != "") {
                endPoint += `&archetype=${store.search}`;
            }

            axios.
            get(endPoint)
            .then(res => {
                console.log(res.data.data);
                store.cardList = res.data.data;
            }).catch(err => {
                console.log(err);
            });
        }
    },
    created() {
        this.getCard();
    },
    components: {
        AppHeader,
        SelectRace,
        CardList,
    }
}
</script>

<template>
    <AppHeader message="Yu-gi-oh Card Finder" />
    <main>
        <SelectRace @search="getCard()" />
        <CardList />
    </main>
</template>

<style lang="scss">
@use './style/general.scss';

main {
    padding-top: 20px;
}

</style>
