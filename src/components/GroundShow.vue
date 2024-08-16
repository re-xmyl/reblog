<script setup lang="ts">
</script>

<template>
    <div id="gs">
        <div id="gd">
            <div id="words">
                野狗不需要墓碑<br/>
                狂奔到腐烂就好
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
        background-position:center;
        display: flex;
        flex-direction: column;

    }

    #words{
        font-size: xx-large;
        font-weight: bold;
        align-items: center;
        text-align: center;
        color:white;
        position: absolute;
        left:0;
        top:35%;
        width: 100%;
        height: auto;
        z-index: 5;
        letter-spacing: 5px;
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