<template>
    <div class="Home">
        <div class="wrap">
            <Search class="search"></Search>
            <banner class="banner"></banner>
        </div>
        <proList></proList>
        <MenuBar></MenuBar>
    </div>
</template>

<script>
    import Search from "../../components/Search.vue";
    import Banner from "./components/banner";
    import proList from "./components/proList.vue";

    export default {
        name: "Home",
        components: {
            Banner,
            Search,
            proList
        }
    }
</script>

<style scoped>
    .Home .wrap{
        width: 100%;
        height: 474px;
        position: relative;
    }
    .Home .search{
        position: absolute;
        z-index: 2;
        left: 0;
        right: 0;
        margin: 14px auto 0 auto;
    }
    .Home .banner{
        position: absolute;
        z-index: 1;
        left: 0;
        right: 0;
        margin: 0 auto;
    }
</style>