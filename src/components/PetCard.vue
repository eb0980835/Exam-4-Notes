<script>
    export default{
        props: ['pet'] // Makes the pet list a prop within PetCard
    }
</script>

<template>
    <div class="card">
        <h3>{{ pet.name }}</h3>
        <p>Type: {{ pet.type }}</p>
        <p>Age: {{ pet.age }}</p>
        <p v-if="pet.adopted">Status: Adopted</p> <!-- If pet.adopted = true, print Status: Adopted-->
        <p v-else>Status: Available</p> <!-- If pet.adopted = false, print Status: Available-->
    </div>
</template>