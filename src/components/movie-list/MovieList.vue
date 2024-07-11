<template>
    <ul class="movie-list list-group">
        <MovieItem v-for="movie in movies" :key="movie.id" :movie="movie" @onToggle="$emit('onToggle', $event)" @onRemove="$emit('onRemove', movie.id)" />
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
                required: true,
            },
        },
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
