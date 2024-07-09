<script>
export default {
    name: 'SingleCharacter',
    props: ['info']
}
</script>

<template>
    <div class="character text-center">
        <img class="img-fluid mb-3" :src="info.image" :alt="info.name">
        <h4> {{ info.name }} </h4>
        <div> Status: {{ info.status }} </div>
        <div class="font-weight-bold"> Specie: {{ info.species }} </div>
        <div class="font-weight-bold"> Birth Planet: {{ info.origin.name }} </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.character {
    img {
        border-radius: 50%;
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