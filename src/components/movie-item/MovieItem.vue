<template>
    <li class="list-group-item d-flex justify-content-between" :class="[{ like: movie.like }, { favorite: movie.favorite }]">
        <span class="list-gorup-item-label">{{ movie.name }}</span>
        <input type="number" class="list-group-item-input" :defaultValue="movie.viewers" />
        <div class="d-flex justify-content-content align-items-center">
            <button type="button" class="btn-cookie btn-sm">
                <i class="fas fa-cookie"></i>
            </button>

            <button class="btn-trash btn-sm">
                <i class="fas fa-trash"></i>
            </button>

            <i class="fas fa-star"></i>
        </div>
    </li>
</template>

<script>
    export default {
        props: {
            movie: {
                type: Object,
                required: true,
            },
        },
    };
</script>

<style scoped>
    .list-group-item {
        border: none;
        background: none;
        padding: 10px 20px;
        border-bottom: 1px solid #3d5a80;
    }
    .list-group-item:last-child {
        border-bottom: none;
    }
    .list-group-item > span {
        line-height: 35px;
        font-size: 20px;
        cursor: pointer;
        width: 550px;
    }
    .list-group-item > input {
        line-height: 35px;
        font-size: 20px;
        text-align: center;
        border: none;
        outline: none;
        background: transparent;
    }
    .list-group-item button {
        width: 35px;
        height: 35px;
        margin: 3px;
        font-size: 17px;
        border: none;
        /* background: transparent; */
    }
    .list-group-item .btn-cookie {
        color: #e09f3e;
    }
    .list-group-item .btn-trash {
        color: #e5383b;
    }
    .list-group-item .fa-star {
        width: 35px;
        height: 35px;
        text-align: center;
        line-height: 35px;
        font-size: 16px;
        color: #ffd700;
        transition: 0.3s all;
        transform: translateX(30px);
        opacity: 0;
    }
    .list-group-item.like .fa-star {
        opacity: 1;
        transform: translateX(0px);
    }
    .list-group-item.favorite .list-gorup-item-label,
    .list-group-item.favorite .list-group-item-input {
        color: #e09f3e;
    }
</style>
