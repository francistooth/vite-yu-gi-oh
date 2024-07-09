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
        <div class="font-weight-bold"> Effect: {{ info.desc }} </div>
        <div class="font-weight-bold"> Race: {{ info.archetype }} </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

// .character {
    // img {
    //     border-radius: 50%;
    // }
// }

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