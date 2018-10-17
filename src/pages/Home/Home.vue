<template>
    <div class="Home">
        <div class="wrap">
            <Search class="search"></Search>
            <banner class="banner"></banner>
        </div>
        <MenuBar></MenuBar>
    </div>
</template>

<script>
    import Search from "../../components/Search.vue";
    import Banner from "./components/banner";

    export default {
        name: "Home",
        components: {
            Banner,
            Search
        }
    }
</script>

<style scoped>
    .Home{
        width: 750px;
        height: auto;

    }
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
        margin: 0 auto;
        margin-top: 14px;
    }
    .Home .banner{
        position: absolute;
        z-index: 1;
    }
</style>