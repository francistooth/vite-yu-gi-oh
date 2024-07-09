<script>
export default {
    name: 'SingleCard',
    props: ['info']
}
</script>

<template>
    <div class="character text-center">
        <img class="img-fluid mb-3" :src="info.card_images[0].image_url" :alt="info.name">
        <h4> {{ info.name }} </h4>
        <div> Type: {{ info.type }} </div>
        <p> Effect: {{ info.desc }} </p>
        <div v-if="info.card_prices[0].ebay_price != 0.00" class="font-weight-bold"> Ebay price: &dollar;{{ info.card_prices[0].ebay_price }} </div>
        <div v-else class="font-weight-bold"> Ebay price: no price found </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.character {
    p {
        color: limegreen;
    }
}

h4 {
    text-transform: capitalize;

    &::after {
        content: '';
        display: block;
        width: 40px;
        height: 1px;
        margin: 1rem auto;
        background-color: black;
    }
}
</style>