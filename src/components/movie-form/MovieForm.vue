<template>
    <div class="movie-form">
        <h3>Yagni kino qo'shish</h3>
        <form action="" class="add-form d-flex">
            <input type="text" class="form-control new-movie-label" placeholder="Qanday kino?" />
            <input type="text" class="form-control new-movie-label" placeholder="Nechi marotaba ko'rilgan?" />
            <button type="submit" class="btn btn-outline-dark">Qo'shish</button>
        </form>
    </div>
</template>

<script>
    export default {};
</script>

<style>
    .movie-form {
        margin-top: 2rem;
        padding: 1.5rem;
        background: #fcfaf5;
        border-radius: 16px;
        border: 1px solid #00000071;
    }
</style>
