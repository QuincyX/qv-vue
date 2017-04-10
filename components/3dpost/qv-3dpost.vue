<template>
  <div class="img3d" @mouseenter="my3d($event)" @mouseleave="endmy3d($event)" :style="img3d">
    <div class="v1">
      <slot name="v1"></slot>
    </div>
    <div class="v2">
      <slot name="v2"></slot>
    </div>
    <div class="v3">
      <slot name="v3"></slot>
    </div>
  </div>
</template>
<script>
    export default {
      data(){
        return{
          img3d:{
            backgroundImage:'url('+this.backgroundimg+')'
          }
        }
      },
      props: {
        backgroundimg:String,
        width:String,
        height:String
      },
      methods: {
        my3d(e){
          let thisPX = $(e.target).offset().left;
          let thisPY = $(e.target).offset().top;
          let boxWidth = $(e.target).width();
          let boxHeight = $(e.target).height();
          $(e.target).addClass('threeD');
          $(".threeD").mousemove(function(event) {
            let mouseX = event.pageX - thisPX;
            let mouseY = event.pageY - thisPY;
            let X = mouseX - boxWidth/2;
            let Y = boxHeight/2 - mouseY;
            $(".threeD").css({
              "transform": "rotateY(" + X / 50 + "deg) " + "rotateX(" + Y / 50 + "deg)"
            });
          })
        },
        endmy3d(e){
          $(e.target).removeClass("threeD");
          $(e.target).css({
            "transform": "rotateY(0deg) rotateX(0deg)"
          });
        }
      },
      created(){
        this.img3d.width=this.width
        this.img3d.height=this.height
      },
    }
</script>

<style scoped>
.img3d{
  background-position: top center;
  background-repeat: no-repeat;
  /*background-size:100%;*/
  /*margin:0 auto;*/
  position: relative;
  border-radius: 10px;
  transform-style: preserve-3d;
  transform-origin: 50% 50%;
  transform: rotateY(0deg) rotateX(0deg);
}
.v1>{
  transform: translateZ(0px);
  position: absolute;
  top:20%;
  right:10%;
}
.v2>{
  transform: translateZ(40px);
  position: absolute;
}
.v3>{
  transform: translateZ(80px);
  position: absolute;
}
</style>
