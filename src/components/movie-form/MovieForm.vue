<template>
    <div class="movie-form">
        <h3>Yagni kino qo'shish</h3>
        <form action="" class="add-form d-flex" @submit.prevent>
            <input type="text" class="form-control new-movie-label" placeholder="Qanday kino?" :value="name" @input="name = $event.target.value" />
            <input
                type="number"
                class="form-control new-movie-label"
                placeholder="Nechi marotaba ko'rilgan?"
                :value="viewers"
                @input="viewers = $event.target.value" />
            <button type="submit" class="btn btn-outline-dark" @click="addMovie">Qo'shish</button>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                name: "",
                viewers: "",
            };
        },
        methods: {
            addMovie(e) {
                if (!this.name || !this.viewers) return;
                const newMovie = {
                    name: this.name,
                    viewers: this.viewers,
                    favorite: false,
                    like: false,
                    id: Date.now(),
                };
                this.$emit("createMovie", newMovie);
                (this.name = ""), (this.viewers = "");
            },
        },
    };
</script>
F
<style>
    .movie-form {
        margin-top: 2rem;
        padding: 1.5rem;
        background: #fcfaf5;
        border-radius: 16px;
        border: 1px solid #00000071;
    }
</style>
