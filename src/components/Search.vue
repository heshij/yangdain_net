<template>
    <div class="Search">
        <form action="">
            <input
                    type="text"
                    placeholder="Montagne jeunesse"
                    class="search"
                    @click="toSearchPage()"
            >
            <span
                    class="iconfont search_btn"
                    @click="toSearchPage()"
            >&#xe61b;</span>
        </form>
    </div>
</template>

<script>
    export default {
        name: "Search",
        methods: {
            toSearchPage() {
                this.$router.push('SearchPage');
            }
        }
    }
</script>

<style scoped>
    .Search form {
        width: 516px;
        height: 62px;
        border-radius: 12px;
        overflow: hidden;
        display: block;
        margin: 0 auto;
        opacity: 0.7;
        font-size: 28px;
    }

    .Search form .search {
        width: 456px;
        height: inherit;
        float: left;
        padding-left: 22px;
        box-sizing: border-box;
    }

    .Search form .search_btn {
        width: 60px;
        height: inherit;
        float: left;
        text-align: center;
        line-height: 62px;
        font-size: 40px;
        background-color: #fff;
    }
</style>