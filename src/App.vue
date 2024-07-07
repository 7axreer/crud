<template>
    <div class="app font-monospace">
        <div class="content">
            <AppInfo />
            <div class="search-pranel">
                <SearchPanel />
                <AppFilter />
            </div>
            <MovieList :movies="movies"/>
            <MovieForm />
        </div>
    </div>
</template>

<script>
    import AppInfo from "@/components/app-info/AppInfo.vue";
    import SearchPanel from "@/components/search-panel/SearchPanel.vue";
    import AppFilter from "@/components/app-filter/AppFilter.vue";
    import MovieList from "@/components/movie-list/MovieList.vue";
    import MovieForm from "./components/movie-form/MovieForm.vue";

    export default {
        components: {
            AppInfo,
            SearchPanel,
            AppFilter,
            MovieList,
            MovieForm,
        },
        data() {
            return {
                movies: [
                    {
                        name: "Omar",
                        viewers: 881,
                        favorite: false,
                        like: true,
                    },
                    {
                        name: "Empire of Osmon",
                        viewers: 481,
                        favorite: false,
                        like: false,
                    },
                    {
                        name: "Ertugrul",
                        viewers: 781,
                        favorite: true,
                        like: true,
                    },
                ],
            };
        },
    };
</script>

<style scoped>
    .app {
        height: 100vh;
        color: #000;
    }
    .content {
        width: 1000px;
        min-height: 700px;
        background: #fff;
        margin: 0 auto;
        padding: 5rem 0;
    }

    .search-pranel {
        margin-top: 2rem;
        padding: 1.5rem;
        background: #fcfaf5;
        border-radius: 16px;
        border: 1px solid #00000071;
    }
</style>
