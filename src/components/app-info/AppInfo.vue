<template>
    <div class="app-info">
        <p class="fs-3 text-uppercase">Barcha kinolar soni: {{ allMovieCount }}</p>
        <p class="fs-4 text-uppercase">Ko'rilgan kinolar soni: {{favMovieCount}}</p>
    </div>
</template>

<script>
    export default {
        props: {
            allMovieCount: {
                type: Number,
                required: true,
            },
            favMovieCount: {
                type: Number,
                required: true,
            },
        },
    };
</script>

<style scoped>
    .app-info {
        padding: 1.5rem;
        border-radius: 4px;
        border: 1px solid #00000071;
        border-radius: 16px;
        background: #fcfaf5;
    }
</style>
