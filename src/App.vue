<script setup lang="ts">
import SearchBox from './components/SearchBox.vue';
import GroundShow from './components/GroundShow.vue';
</script>

<template>
  <header id="nav">
    <div id="nav-left">
      <img src="/head.svg"/>
      <div>
          ReBlog
      </div>
    </div>  
    <div id="nav-mid">
      <div class="nav-word">
        <a>首页</a>
      </div>
      <div class="nav-word">
        <a>分类</a>
      </div>
      <div class="nav-word">
        <a>关于</a>
      </div>
      <div class="nav-word">
        <a>订阅</a>
      </div>
    </div>
    <div id="nav-right">
      <SearchBox></SearchBox>
    </div>
  </header>
  <main>
      <GroundShow></GroundShow>
      <div id="article_summarys"></div>
      <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  </main>
  <footer id="ifooter">
    <div>Copyright © 2024 Re.Blog</div> 
    <div><strong style="font-weight: bold;">QQ:</strong>841189483 &nbsp;&nbsp;&nbsp;<strong style="font-weight: bold;">Email:</strong>841189483@qq.com</div>
  </footer>
</template>

<style scoped>
main{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

#article_summarys{
  width: 70%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#nav{
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  padding:5px 10px;
  background-color: rgb(255, 255, 255);
  z-index: 999;
  border-bottom: 1px solid rgba(136, 136, 136, 0.3);
}

#nav-left{
  width: 350px;
  position:relative;
  left:15%;
  display: flex;
  gap:20px;
}

#nav-left img{
  width: 30px;
  height:30px;

}

#nav-left div{
  font-weight: bold;
}

#nav-mid{
  display: flex;
  flex-direction: row;
  gap:40px;
  position: relative;
  width: 300px;
  align-items: center;
  justify-content: center;
}
#nav-right{
  width: 350px;
  position:relative;
  right:5%;
}

#ifooter{
  display: flex;
  flex-direction: column;
  gap:10px;
  align-items: center;
  justify-content: center;
  width: 100%;
  background-color: black;
  color:white;
}
</style>
