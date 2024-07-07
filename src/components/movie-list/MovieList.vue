<template>
    <ul class="movie-list list-group">
        <MovieItem v-for="(movie, index) in movies" :key="index" :movie="movie" />
    </ul>
</template>

<script>
    import MovieItem from "../movie-item/MovieItem.vue";
    export default {
        components: {
            MovieItem,
        },
        props: {
            movies: {
                type: Array,
                required: true
            }
        }
    };
</script>

<style>
    .movie-list {
        border-radius: 16px;
        margin-top: 2rem;
        padding: 1.5rem;
        background: #fcfaf5;
        border: 1px solid #00000071;
    }
</style>
