<script setup lang="ts">
import SearchBox from './components/SearchBox.vue';
import GroundShow from './components/GroundShow.vue';
</script>

<template>
  <header id="nav">
    <div id="nav-left">
      <img>
      <div>

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
      <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  </main>
  <footer id="ifooter">
    <div>Copyright © 2024 Re.Blog</div> 
    <div><strong style="font-weight: bold;">QQ:</strong>841189483 &nbsp;&nbsp;&nbsp;<strong style="font-weight: bold;">Email:</strong>841189483@qq.com</div>
  </footer>
</template>

<style scoped>
main{
  width: 70%;
  display: flex;
  flex-direction: column;
  position: relative;
  align-items: center;
  justify-content: center;
}
#nav{
  display: flex;
  flex-direction: row;
  width: 70%;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  left:15%;
  padding:5px 10px;
}

#nav-left{
  width: 350px;
}

#nav-mid{
  display: flex;
  flex-direction: row;
  gap:10px 20px;
  position: relative;
  width: 300px;
  align-items: center;
  justify-content: center;
}
#nav-right{
  width: 350px;
}

#ifooter{
  display: flex;
  flex-direction: column;
  gap:10px;
  align-items: center;
  justify-content: center;
}
</style>
