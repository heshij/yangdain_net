<template>
    <div>
        <span @click="toGo()">返回</span>
        <Search></Search>
        我是搜索页面
    </div>
</template>

<script>
    import Search from "../../components/Search";

    export default {
        name: "SearchPage",
        components: {
            Search
        },
        methods: {
            toGo() {
                this.$router.go(-1);
            }
        }
    }
</script>

<style scoped>

</style>