<template>
    <input type="text" class="form-control search-input" placeholder="Kinolarni qidirish" :value="term" @input="liveChangeTerm" />
</template>

<script>
    export default {
        props: {
            changeTerm: {
                type: Function,
                required: true,
            },
        },
        data() {
            return {
                term: "",
            };
        },
        methods: {
            liveChangeTerm(e) {
                this.term = e.target.value;
                this.changeTerm(this.term)
            },
        },
    };
</script>

<style scoped>
    .search-input {
        padding: 0.5rem;
        border: 1px solid #00000071;
        border-radius: 6px;
        background: #fcfaf5;
        margin-bottom: 1rem;
    }
</style>
>
