<script>
import { store } from '../store.js';
export default {
    name: 'HeaderApp',
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <section class="header-container">
        <h1>Boolflix</h1>

        <div class="searchbar">
            <label for="site-search">Search movies:</label>
            <input type="text" id="site-search" v-model="store.searchedText">
            <button @click="$emit('searchedText', store.searchedText)">Search</button>
        </div>

    </section>
</template>

<style lang="scss" scoped>
@use '../styles/style.scss' as *;

.header-container {
    background-color: #141414;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;

    h1 {
        font-size: 3rem;
        text-align: center;
        padding: 1rem;
        color: red;
        text-transform: uppercase;
    }

    .searchbar {
        padding: 2rem;

        label,
        input,
        button {
            margin-right: 2rem;
            text-transform: uppercase;
        }

        label {
            font-size: 1rem;
        }

        input {
            font-size: 1rem;
        }

        button {
            padding: 0.5rem 1rem;
            font-size: 1rem;
            font-weight: 300;
            color: white;
            background-color: red;
            border: none;
            border-radius: 5px;
        }
    }
}
</style>