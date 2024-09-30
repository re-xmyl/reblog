<script setup lang="ts">
import SearchBox from './components/SearchBox.vue';
import GroundShow from './components/GroundShow.vue';
import { onMounted } from 'vue';
//平滑滚动
const lerp = (start: number, end: number, amt: number) => (1 - amt) * start + amt * end; 
const damp = (x: number, y: number, lambda: number, dt: number) => lerp(x, y, 1 - Math.exp(-lambda * dt))
class smroll{
    lastTime:number
    lerp:number
    toPos:number
    isRunning:Boolean
    content:HTMLElement
    constructor(lp = 0.1){
      this.lastTime = performance.now()
      this.lerp = lp
      this.isRunning = false
      this.content = document.documentElement
      this.toPos = this.content.scrollTop
      this.content.addEventListener("wheel",(e)=>{
        e.preventDefault()
        this.isRunning = true
        this.toPos = this.toPos + e.deltaY
        let maxHeight = this.content.scrollHeight - this.content.clientHeight
        if(this.toPos < 0 ){
          this.toPos = 0
        }
        else if(this.toPos > maxHeight){
          this.toPos = maxHeight
        }
      },{passive:false})
    }

    update(value:number){
        this.content.scrollTop = value
    }

    advance(dt:number){
      let cp = false
      let value = 0
      value = damp(this.content.scrollTop, this.toPos, this.lerp * 60, dt)
      console.log("value:",Math.round(value))
      console.log("toPos:",Math.round(this.toPos))
      if(Math.round(value) === Math.round(this.toPos)){
        cp = true
      }
      this.update(value)
      if(cp) {
        this.isRunning = false
        console.log("yes")
      }
    }

    raf(time:number){
      let dt:number
      if(!this.isRunning) {
        this.lastTime = time
        return
      }
      else{
          dt = time - this.lastTime
          this.lastTime = time
      }
      this.advance(dt*0.001)
    }
}

onMounted(()=>{
  let sl = new smroll()
  function raf(time:number){
    sl.raf(time)
    requestAnimationFrame(raf)
  }
  requestAnimationFrame(raf)
})

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
    <div class="footer-words">Copyright © 2024 Re.Blog</div> 
    <div class="footer-words"><strong style="font-weight: bold;">QQ:</strong>841189483 &nbsp;&nbsp;&nbsp;<strong style="font-weight: bold;">Email:</strong>841189483@qq.com</div>
  </footer>
</template>

<style scoped>
main{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.nav-word{
  border: solid 3px white;
  border-radius: 4px;

}

.nav-word a{
  font-weight: bold;
  font-size: 15px;
  color: #2c3e50;
}

.nav-word:hover{
  border-bottom: solid 3px black;
  transition: border-color 0.3s ease-in ;
}

.nav-word a:hover{
  color:black;
  transition: color 0.3s ease-in;
}


.footer-words{
  color: #cecbcb;
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
  left:-10px;
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
  right:7%;
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
  padding: 10px 0;
}
</style>
