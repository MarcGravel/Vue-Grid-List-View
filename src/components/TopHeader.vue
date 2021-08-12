<template>
    <div id="topHeader">
        <h1>Vue Grid/List View</h1>
    </div>
</template>

<script>
    export default {
        name: "TopHeader"
    }
</script>

<style scoped>
    #topHeader {
        width: 100vw;
        height: 15vh;
        background-color: rgb(115, 187, 250);
        display: grid;
        justify-items: center;
        align-items: center;
    }
    h1 {
        color: white;
    }
</style>