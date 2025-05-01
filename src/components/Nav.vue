<script>
export default {
    data() {
        return {
            searchName: ''
        }
    },
    methods: {
        search() {
            this.$emit('search-pet', this.searchName); // Triggers custom search-pet
        }
    }
}
</script>

<template>
    <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/pets">View Pets</router-link>

        <div>
            <input v-model="searchName" type="text" placeholder="Enter pet name"> <!-- v-model creates 2 way data binding -->
            <button @click="search">Search</button> <!-- Runs search() when button is clicked -->
            <!--@click is click event-->
        </div>
    </nav>
</template>