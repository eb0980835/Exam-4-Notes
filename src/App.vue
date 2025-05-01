<!-- Creating a Vue project -->
  <!-- npm create vue@latest -->
  <!-- Check "Router" -->
  <!-- Run first command in terminal -->
  <!-- code . -->
  <!-- Run other commands in VS Code terminal -->
  <!-- Use npm run dev to get live server -->

  <!-- Format document issues may arise -->

<script>
import Nav from './components/Nav.vue'

export default {
  components: {Nav},
  data() {
    return {
      pets: [
        {id: 1, name: "Buddy", type: "Dog", age: 2, adopted: true},
        {id: 2, name: "Mittens", type: "Cat", age: 4, adopted: false},
        {id: 3, name: "Tweety", type: "Bird", age: 1, adopted: true},
        {id: 4, name: "Shadow", type: "Dog", age: 5, adopted: false},
      ],
      searchResult: ''
    }
  },
  methods: {
    handleSearch(name) {
      const pet = this.pets.find(pet => pet.name.toLowerCase() === name.toLowerCase()); // Sets pet to pet with name of what was searched
      if (pet) {
        this.searchResult = `${pet.name} is ${pet.adopted ? "adopted" : "available"}`; // If pet is adopted, display "adopted" and if not, display "available"
      } else {
        this.searchResult = `No pet found by the name ${name}`;
      }
    }
  }
}
</script>

<template>
  <div>
    <Nav @search-pet="handleSearch"/> <!--runs search-pet event and runs handleSearch()-->
    <p>{{ searchResult }}</p>
    <router-view :pets="pets"/>
  </div>
</template>