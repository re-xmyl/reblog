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
                <a>
                    <img src="/next.svg" alt="next"/>
                </a>
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
        font-size: 63px;
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
        font-family: STXingkai;
    }

    #next-button{
        width: 100%;
        height: auto;
        align-items: center;
        position: absolute;
        left: 0;
        bottom: 0;
        z-index: 5;
        text-align: center;
    }

    #next-button a img{
        width: 40px;
        height: 40px;
        margin-bottom: 15px;
        animation: animate-next 1s linear infinite alternate;
    }


    @keyframes animate-next {
        0% {
            opacity:1;
        }    
        100%{
            opacity:0.2;
            transform: translateY(10px);
        }
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