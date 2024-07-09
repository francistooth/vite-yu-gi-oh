<script>
import SingleCard from './SingleCard.vue';

// store import

import { store } from '../store';

export default {
    name: 'CardList',
    components: {
        SingleCard,
    }, 
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <section class="container">
        <div class="row">
            <div v-for="card in store.cardList" :key="card.id" class="col-6 col-md-4 col-lg-3 mb-5">
                <SingleCard :info="card"/>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">

</style>