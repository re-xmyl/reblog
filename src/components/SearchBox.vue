<script setup lang="ts">
    import { onMounted } from 'vue';

    onMounted(()=>{
        let ft1 = true
        const inputBox = document.getElementById("search-ct") as HTMLElement
        const searchBox = document.getElementById("search-box") as HTMLElement
        inputBox.addEventListener("focus",()=>{
            ft1 = false
            searchBox.style.width = "300px"
            searchBox.style.borderColor="rgb(0,0,0,1)"
            searchBox.classList.remove("animation-shrink")
            searchBox.style.pointerEvents="none"
        })
        inputBox.addEventListener("blur",()=>{
            searchBox.style.width = "35px"
            searchBox.style.borderColor="rgb(0,0,0,0)"
            searchBox.classList.add("animation-shrink")
            searchBox.offsetHeight
            searchBox.style.pointerEvents="auto"
        })
        searchBox.addEventListener("mouseleave",()=>{
            if(ft1) {
                searchBox.classList.add("animation-shrink")
                ft1 = false
            }
        })

    })
</script>
<template>
<div id="search-box">
    <img id="search-ic" src="/search.svg" alt="搜索：" />
    <input id="search-ct"/>
</div>
</template>

<style scoped>
    #search-box{
        position:relative;
        display: flex;
        flex-direction: row;
        border: rgb(0,0,0,0) solid 2px;
        border-radius:11px;
        width:35px;
        height:35px;
        margin:2px 5px;
    }

    #search-ic{
        margin: 5px 5px;
        width: 25px;
        height:25px;
    }

    #search-ct{
        border: none;
        width:80%;
        outline: none;
        line-height:35px ;
        font-size: 18px;
        text-align: left;
        background-color: transparent;
    }

    #search-box:hover{
        width: 300px;
        border-color: rgb(0,0,0,1);
        animation: box-extend 0.6s ease-in-out forwards;
    }

    .animation-shrink{
        animation:box-shrink 0.6s ease-in-out;
    }

    @keyframes box-extend{
        0%{width:35px;border-color: rgb(0,0,0,0);}
        30%{
            border-color: rgb(0,0,0,1);
        }
        100%{
            width:300px;
            border-color: rgb(0,0,0,1);
        }
    }

    @keyframes box-shrink{
        0%{width: 300px;border-color: rgb(0,0,0,1);}
        80%{
            border-color: rgb(0,0,0,1);
        }
        100%{
            width:35px;
            border-color: rgb(0,0,0,0);
        }
    }

</style>