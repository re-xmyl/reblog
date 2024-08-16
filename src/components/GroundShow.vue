<script setup lang="ts">
</script>

<template>
    <div id="gs">
        <div id="gd">
            <div id="words">

            </div>
            <div id="next-button">

            </div>
        </div>
        <div id="mask">

        </div>
    </div>
</template>

<style scoped>
    #gs{
        position: relative;
        width: 100%;
        height:100vh;
    }

    #gd{
        background: url("/backgd-1920x997.png") no-repeat;
        width: 100%;
        height:100vh;
        background-size:cover;
        background-position:center
    }

    #mask{
        position: absolute;
        left:0;
        top: 0;
        z-index: 3;
        width: 100%;
        height: 100%;
        background-color: rgba(156, 98, 147, 0.3);
    }

</style>    