<script setup lang="ts">
  
</script>
<template>
<div id="search-box">
    <a id="search-ic">
        <img src="/search.svg" alt="搜索：" style="width: 25px;height:25px;"/>
    </a>
    <input id="search-ct"/>
</div>
</template>

<style scoped>
    #search-box{
        position:relative;
        display: flex;
        flex-direction: row;
        border: rgb(0,0,0,0) solid 2px;
        border-radius:7px;
        width:300px;
        height:35px;
    }

    #search-ic img{
        margin: 5px 5px;
    }

    #search-ct{
        border: none;
        width:85%;
        outline: none;
        line-height:35px ;
        font-size: 18px;
        text-align: left;
    }
</style>