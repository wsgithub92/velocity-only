<template>
  <div class="velocity-wrapper">
    <h4 class="velocity-text">Velocity内置动画展示</h4>

    <div class="btnBox">
      <div class="btn" @click="velocityAnimation">velocity基本使用动画</div>
      <div class="btn" v-for="(item,index) in velocityList" :key="item+index" @click="velocityAnimationUi(item)">{{item}}</div>
    </div>

    <div class="velocity-dom"></div>


    <div class="colorBox"></div>

    <div class="topBtn" @click="toTop">置顶</div>
  </div>
</template>

<script>
import Velocity from 'velocity-animate/velocity.min'; //基础库
// eslint-disable-next-line
import VelociityUi from 'velocity-animate/velocity.ui.min'; //动画库


export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
  return {
    velocityList:[
        'callout.bounce',
        'callout.shake',
        'callout.flash',
        'callout.pulse',
        'callout.swing',
        'callout.tada',
        'transition.fadeIn',
        'transition.fadeOut',
        'transition.flipXIn',
        'transition.flipXOut',
        'transition.flipYIn',
        'transition.flipYOut',
        'transition.flipBounceXIn',
        'transition.flipBounceXOut',
        'transition.flipBounceYIn',
        'transition.flipBounceYOut',
        'transition.swoopIn',
        'transition.swoopOut',
        'transition.whirlIn',
        'transition.whirlOut',
        'transition.shrinkIn',
        'transition.shrinkOut',
        'transition.expandIn',
        'transition.expandOut',
        'transition.bounceIn',
        'transition.bounceUpIn',
        'transition.bounceUpOut',
        'transition.bounceDownIn',
        'transition.bounceDownOut',
        'transition.bounceLeftIn',
        'transition.bounceLeftOut',
        'transition.bounceRightIn',
        'transition.bounceRightOut',
        'transition.slideUpIn',
        'transition.slideUpOut',
        'transition.slideDownIn',
        'transition.slideDownOut',
        'transition.slideLeftIn',
        'transition.slideLeftOut',
        'transition.slideRightIn',
        'transition.slideRightOut',
        'transition.slideUpBigIn',
        'transition.slideUpBigOut',
        'transition.slideDownBigIn',
        'transition.slideDownBigOut',
        'transition.slideLeftBigIn',
        'transition.slideLeftBigOut',
        'transition.slideRightBigIn',
        'transition.slideRightBigOut',
        'transition.perspectiveUpIn',
        'transition.perspectiveUpOut',
        'transition.perspectiveDownIn',
        'transition.perspectiveDownOut',
        'transition.perspectiveLeftIn',
        'transition.perspectiveLeftOut',
        'transition.perspectiveRightIn',
        'transition.perspectiveRightOut'
    ]
  };
},
  methods:{
    //velocity基础动画的使用
    velocityAnimation(){
      const dom  = document.querySelector('.velocity-dom');
      Velocity(dom,{width:'300px'},{
        duration:1000,
        easing:'easeInSine'
      });
      setTimeout(()=>{
        Velocity(dom,{height:'300px',opacity:'0.5'},{
          duration:500,
          easing:'easeInCirc',
          queue: false, //强制并执行新动画，第一个动画跟第二个动画一起进行
        })
      },500)
    },

    //内置动画效果
    velocityAnimationUi(type){
      const dom  = document.querySelector('.velocity-dom');
      Velocity(dom,'stop'); //停止其他在执行的动画
      Velocity(dom,type,{duration: 1000});
    },

    //置顶方法
    toTop(){
      const body = document.querySelector('body');
      Velocity(body,'scroll',{ duration: 500, easing: "easeOutQuart" })

    }
  }
}
</script>

<style scoped>
.velocity-wrapper{
  width: 90%;
  margin: 0 auto;
  position: relative;
}

.velocity-text{
  margin:20px 0;
}

.btnBox {
  display: flex;
  flex-wrap: wrap;
}

.btn{
  display: inline-block;
  padding: 10px;
  background-color: #ff9048;
  color: white;
  cursor: pointer;
  margin: 0 10px 10px 0 ;
  border-radius: 4px;
  font-size: 14px;
}

.velocity-dom{
  width: 100px;
  height: 100px;
  background-color: cyan;
  margin: 50px 0;
}

.colorBox{
  width: 100%;
  height: 2000px;
  background-image: linear-gradient(#e66465, #9198e5);
}

.topBtn{
  width: 80px;
  height: 80px;
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 999;
  border-radius: 50%;
  background-color: coral;
  text-align: center;
  line-height: 80px;
  color: white;
  cursor: pointer;
}
</style>
