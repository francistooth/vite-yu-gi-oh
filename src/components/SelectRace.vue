<script>
import { store } from '../store';

// axios import

import axios from 'axios';

export default {
    name: 'SelectRace',
    data() {
        return {
            store,
        }
    },
    methods: {
        getArch(){
            axios.
            get(store.archUrl)
            .then(res => {
                console.log(res.data);
                store.archList = res.data;
            }).catch(err => {
                console.log(err);
            });
        }
    },
    mounted() {
        this.getArch();
    },
}
</script>

<template>
    <div class="container mb-3">
        <label class="labels" for="raceSelect"> Filter by race:  </label>
        <select v-model="store.search" @change="$emit('search')">
            <option value=""></option>
            <option v-for="arch in store.archList" :value="arch.archetype_name">
                {{ arch.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.labels {
    margin-right: 10px;
}
</style>