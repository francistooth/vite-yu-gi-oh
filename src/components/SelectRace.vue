<script>
import { store } from '../store';

export default {
    name: 'SelectRace',
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="container mb-3">
        <label class="labels" for="raceSelect"> Filter by race:  </label>
        <select v-model="store.search" @change="$emit('search')">
            <option value=""></option>
            <option value="Alien"> Alien </option>
            <option value="Infernoble Arms"> Infernoble Arms</option>
            <option value="Noble Knight"> Noble Knight </option>
            <option value="Ally of Justice"> Ally of Justice </option>
            <option value="Melodious"> Melodious </option>
            <option value="Gagaga"> Gagaga </option>
        </select>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.labels {
    margin-right: 10px;
}
</style>