<template>
  <div class="background">
    <div class="title">
      <div class="soultest">
        <img src="../../assets/images/earth.jpeg" style="width:20%;height: 80%;">
        <p style="color:aliceblue">灵魂测试</p>
      </div>
      <p style="position:absolute;left:47.5%;font-size: 50px;font-family:'Times New Roman', Times, serif;color: aliceblue;">Soul</p>
      <div class="select">
        <img src="../../assets/images/select.jpg" style="width:20%;height: 80%;">
        <p style="color:aliceblue">筛选</p>
      </div>
      <img src="../../assets/images/ring.jpg" style="width:10vh;height: 10vh;right:5vh;position: absolute;top:6vh;">
    </div>
    <soul-star-box></soul-star-box>
    <p class="center">当前<span style="color: aquamarine;">126566</span>人在线</p>
    <div class="adv">
      <img src="../../assets/images/logo1.jpg" class="img">
      <p style="margin-right: 10px;"><span style="color: orange;">同城卡</span>/<span style="color: orange;">加速卡</span>/<span style="color: orange;">定位卡</span> ></p>
    </div>
    <div class="botton">
      <div class="soulmatch">
        <p style="margin-top: 2vh;margin-left: 5vh;font-size: 30px;color:aliceblue">灵魂匹配</p>
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 15px;color:aliceblue">今日剩余20次</p>
        <botton class="matchbotton">开始匹配</botton>
      </div>
      <div class="mengmian">
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 20px;color:aliceblue">蒙面酒馆</p>
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 15px;color:aliceblue">猜个拳，赢了问Ta问题</p>
      </div>
      <div class="wordmatch">
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 30px;color:aliceblue">语音匹配</p>
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 15px;color:aliceblue">今日剩余3次</p>
      </div>
      <div class="partytalk">
        <p style="margin-top: 2vh;margin-left: 5vh;font-size: 30px;color:aliceblue">群聊派对</p>
        <p style="margin-top: 1vh;margin-left: 5vh;font-size: 15px;color:aliceblue">听听大家在聊什么</p>
        <botton class="matchbotton">进入派对</botton>
      </div>
      <div class="mengmianparty">
        <p style="margin-top: 3vh;margin-left: 5vh;font-size: 30px;color:aliceblue">萌面匹配</p>
        <p style="margin-top: 2vh;margin-left: 5vh;font-size: 15px;color:aliceblue">剩余13次</p>
      </div>
      <div class="lunbo">
        <img :src="currentImage.src" alt="image" />
        <p class="lunbotext">{{ currentImage.text }}</p>
        <p class="lunbotext1">{{ currentImage.text1 }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import SoulStarBox from './components/Box'
export default {
  data () {
    return {
      images: [
        { src: require('@/assets/images/lunbo1.jpg'), text: '星球实验室', text1: '超多有趣新玩法' },
        { src: require('@/assets/images/lunbo2.png'), text: '兴趣群组', text1: '总有一群人懂你' }
        // 添加更多图片和内容
      ],
      currentIndex: 0
    }
  },
  computed: {
    currentImage () {
      return this.images[this.currentIndex]
    }
  },
  mounted () {
    setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % this.images.length
    }, 4000)
  },
  name: 'SoulStar',
  components: {
    SoulStarBox
  }
}
</script>

<style>
.title{
  width:100%;
  height:5vh;
  /* background-color: aliceblue; */
  display: flex;
  align-items: center; /* 垂直居中 */
}
.soultest{
  width:10%;
  height:3vh;
  position: absolute;
  left:5vh;
  background-color:rgb(17, 5, 128,0.3);
  border-radius: 20px;
  display: flex;
  align-items: center; /* 垂直居中 */
  justify-content: space-around;
  border: 1cap;
}
.select{
  width:10%;
  height:3vh;
  position: absolute;
  right:5vh;
  background-color:rgb(17, 5, 128,0.3);
  border-radius: 20px;
  display: flex;
  align-items: center; /* 垂直居中 */
  justify-content: space-around;
  border: 1cap;
}
.background {
  background-color: rgb(8, 8, 14);
  width: 100%;
  height: 100vh; /* 你可以根据需要调整这个值 */
}
.center {
  position: absolute;
  text-align: center;
  top: 50vh;
  left: 47%;
  color:aliceblue;
}
.soul-star-box {
  position: absolute; /* 使用绝对定位 */
  left: 40%; /* 将盒子左侧对齐到父元素的 50% */
  transform: translate(-50%, -50%); /* 通过负的 translate 将盒子完全居中 */
  width: 300px;
  height: 300px;
  transition: 3s linear;
  transform-style: preserve-3d;
  animation: revolution 20s linear 0s infinite;
  border-radius: 20px;
  bottom:80vh;

}
.adv{
  display: flex; /* 使用 Flexbox */
  justify-content: space-between;
  align-items: center; /* 垂直居中 */
  background-color: rgb(213, 228, 228);
  width: 15%;
  height:4vh;
  border-radius: 10px;
  position: absolute;
  left:42%;
  top:55vh;
}
.img{
  margin-left: 10px;
  height:100%;
}
.botton{
  height:35vh;
  width:100%;
  position: absolute;
  top:60vh;
}
.soulmatch{
  width:30%;
  height:17vh;
  background-image: url('../../assets/images/blue.jpeg'); /* 设置背景图片 */
  background-size: cover; /* 背景图片覆盖整个div区域 */
  background-position: center; /* 背景图片居中 */
  /* position: relative;
  margin-left: 5vh;
  margin-top: 2vh; */
  position: absolute;
  top:2vh;
  left:6vh;
  border-radius: 15px;
}
.mengmian{
  width:30%;
  height:8vh;
  background-color: brown;
  position:absolute;
  top:22vh;
  left:6vh;
  border-radius: 15px;
  background-image: url('../../assets/images/perple.jpg'); /* 设置背景图片 */
  background-size: cover; /* 背景图片覆盖整个div区域 */
  background-position: center; /* 背景图片居中 */
}
.wordmatch{
  width:30%;
  height:8vh;
  background-color: brown;
  position:absolute;
  top:2vh;
  left:73vh;
  border-radius: 15px;
  background-image: url('../../assets/images/perple1.jpeg'); /* 设置背景图片 */
  background-size: cover; /* 背景图片覆盖整个div区域 */
  background-position: center; /* 背景图片居中 */
}
.partytalk{
  width:30%;
  height:17vh;
  background-color: brown;
  position:absolute;
  top:13vh;
  left:73vh;
  border-radius: 15px;
  background-image: url('../../assets/images/pink.jpeg'); /* 设置背景图片 */
  background-size: cover; /* 背景图片覆盖整个div区域 */
  background-position: center; /* 背景图片居中 */
}
.mengmianparty{
  width:30%;
  height:13vh;
  background-color: brown;
  position:absolute;
  top:2vh;
  left:140vh;
  border-radius: 15px;
  background-image: url('../../assets/images/blue&perlpe.jpeg'); /* 设置背景图片 */
  background-size: cover; /* 背景图片覆盖整个div区域 */
  background-position: center; /* 背景图片居中 */
}
.lunbo{
  width:30%;
  height:13vh;

  position:absolute;
  top:17vh;
  left:140vh;
  border-radius: 15px;
  overflow: hidden;
}
.matchbotton{
  height: 5vh;
  width:10vh;
  background-color: aliceblue;
  position: absolute;
  top:10vh;
  left:5vh;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 15px;
}
.lunboimg{
  width:100%;
  height:100%;
}
.lunbotext{
  color:brown;
  position: absolute;
  top:2vh;
  font-size: 30px;
  left:5vh;
}
.lunbotext1{
  color:brown;
  position: absolute;
  top:8vh;
  font-size: 15px;
  left:5vh;
}
</style>
