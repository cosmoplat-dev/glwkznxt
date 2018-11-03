<template>
  <div class="home">
    <div>
      <img src="/boiler.jpg" width="800px">
      <p></p>
      <span></span>
      <p class="num" :style="color">{{num}}</p>
      <img src="/fire.png" width="80px" class="fire" :style="opacity">
      <div class="water" :style="height"></div>
    </div>
    <div>
      <button @click="click">效果演示</button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      num:25,
      time:null,
      ok:true,
      color:'color:black',
      opacity:"opacity:0",
      height:"height: 0px;background-color: blue;"
    }
  },
  methods: {
    click(){
      if(this.ok){
        this.ok=false;
        var i = 1;
        var time1 = setInterval(()=>{
          this.num=25;
          i++;
          this.height=`height: ${i*11}px;background-color: blue;`
          if(i===10){
            clearInterval(time1)
          }
        },690)
        setTimeout(()=>{
          this.opacity = "opacity:1";
          this.time = setInterval(()=>{
            
            this.num++;
            this.color='color:red';
            if(this.num===26){
              this.height=`height: ${i*11}px;background-color: rgb(0, 255, 255)`;
            }else if(this.num===27){
              this.height=`height: ${i*11}px;background-color: rgb(0, 255, 255)`;
            }else if(this.num===28){
              this.height=`height: ${i*11}px;background-color: rgb(0, 255, 170)`;
            }else if(this.num===29){
              this.height=`height: ${i*11}px;background-color: rgb(0, 255, 98)`;
            }
            if(this.num===30){
              this.color='color:black';
              this.opacity = "opacity:0";
              this.height=`height: ${i*11}px;background-color: rgb(0, 255, 13)`;
              clearInterval(this.time);
            }
          },3000)
        },7000)
        setTimeout(()=>{
          time2 = setInterval(()=>{
            i--;
            this.height=`height: ${i*11}px;background-color: rgb(0, 255, 13)`;
            if(i===0){
              clearInterval(time2);
              this.ok = true;
            }
          },700)
        },22000)
      }
    }
  },
}
</script>


<style lang="less" scoped>
.home {
  min-width: 1200px;
  background-color: #a6cbe2;
  margin: 0px auto;
  min-height: 730px;
}
.home div:first-child {
  position: relative;
  top:30px;
  width: 1000px;
  display: inline-block;
  margin-left: 100px;
  height: 560px;
}
.home div:last-child{
  display: inline-block;
}
.home div:last-child button{
  width: 120px;
  height: 50px;
  font-size: 20px;
}
.home div:first-child p{
  padding: 0;
  margin: 0;
  height: 38px;
  width: 390px;
  position: absolute;
  top: 0;
  left: 0;
  background-color: #a6cbe2;
}
.home div:first-child span{
  position: absolute;
  width: 120px;
  height: 40px;
  top: 432px;
  left: 680px;
  background-color: #a6cbe2;
}
.home div:first-child .water{
  width: 136px;
  position: absolute;
  bottom: 324px;
  left: 289px;
  z-index: 10;
}
.home div:first-child p.num{
  font-size: 18px;
  position: absolute;
  top: 50px;
  left: 324px;
  width: 18px;
  height: 20px;
}
.home div:first-child img:nth-child(5){
  position: absolute;
  top: 132px;
  left: 321px;
  z-index: 1000;
}
main{
  min-width: 1200px !important;
  margin:0 auto !important;
  padding: 0 !important;
}
</style>
