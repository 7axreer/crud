<template>
    <div class="app font-monospace">
        <div class="content">
            <AppInfo :allMovieCount="movies.length" :favMovieCount="movies.filter((c) => c.favorite).length" />
            <div class="search-pranel">
                <SearchPanel :changeTerm="changeTerm"/>
                <AppFilter />
            </div>
            <MovieList :movies="onSearch(movies, term)" @onToggle="onToggleAdd" @onRemove="onRemoveBtn" />
            <MovieForm @createMovie="createMovie" />
        </div>
    </div>
</template>

<script>
    import AppInfo from "@/components/app-info/AppInfo.vue";
    import SearchPanel from "@/components/search-panel/SearchPanel.vue";
    import AppFilter from "@/components/app-filter/AppFilter.vue";
    import MovieList from "@/components/movie-list/MovieList.vue";
    import MovieForm from "@/components/movie-form/MovieForm.vue";

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
                        favorite: true,
                        like: false,
                        id: 1,
                    },
                    {
                        name: "Empire of Osmon",
                        viewers: 481,
                        favorite: false,
                        like: true,
                        id: 2,
                    },
                    {
                        name: "Ertugrul",
                        viewers: 781,
                        favorite: true,
                        like: false,
                        id: 3,
                    },
                ],
                term: "",
            };
        },
        methods: {
            createMovie(item) {
                this.movies.push(item);
            },
            onToggleAdd({ id, action }) {
                this.movies = this.movies.map((item) => {
                    if (item.id == id) {
                        return { ...item, [action]: !item[action] };
                    }
                    return item;
                });
            },
            onRemoveBtn(id) {
                this.movies = this.movies.filter((c) => c.id !== id);
            },
            onSearch(arr, term) {
                if (term.length == 0) {
                    return arr;
                }

                return arr.filter((e) => e.name && e.name.toLowerCase().indexOf(term) > -1);
            },
            changeTerm(term) {
                this.term = term
            }
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
