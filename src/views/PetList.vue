<script>
  import PetCard from '../components/PetCard.vue' // Imports PetCard component

  export default {
    components: {PetCard}, // PetCard can now be used like an HTML tag
    props: ['pets'] // Makes the pet list a prop within PetList
  }
</script>

<template>
  <div>
    <h2>Available Pets:</h2>
    <div v-for="pet in pets" :key="pet.id"> <!-- Acts like a for loop -->
      <PetCard :pet="pet"/>
    </div>
  </div>
</template>