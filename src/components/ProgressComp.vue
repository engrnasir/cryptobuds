<template>
  <div class="progress">
  <svg width="350" height="350" viewBox="0 0 200 200">  
    <circle cx="100" cy="100" r="84" fill="none" stroke="#1A1919" stroke-width="12" class="outer-circle" />
    <circle cx="100" cy="100" r="74" fill="none" stroke="#666" stroke-width="12" class="outer-circle" />
    <circle cx="100" cy="100" r="74" fill="none" stroke="#F3AD26" stroke-width="12" stroke-dasharray="465" :stroke-dashoffset="dashOffsetCircle" stroke-linecap="round" class="inner-circle"/>
  </svg>
  <div class="percentage">
    {{percentage}}%
  </div>
</div>
</template>

<script>
export default {
    props: ['firstVal', 'totalVal'],
    data () {
    return {
      percentage:0,
      dashOffsetCircle: 0,
    }
    },
    methods: {
      
  },
  mounted(){
    let temp = this.firstVal/this.totalVal 
    temp = Math.ceil(temp*100)
    this.percentage = temp
    this.dashOffsetCircle = 4.65 * temp
    this.dashOffsetCircle = 465 - this.dashOffsetCircle
  }
}
</script>

<style lang="scss" scoped>
@import url(https://fonts.googleapis.com/css?family=Montserrat);
@import url(https://fonts.googleapis.com/css?family=Montserrat);

$colour:hsla(350,100%,25%,1);
$grey:desaturate($colour,90%);
.progress{
  position: relative;
  width: min-content;

  svg{
    transform: rotate(180deg);
    @media only screen and (max-width : 1460px){
      width: 440px;
      height: 440px;
    }
    @media only screen and (max-width : 580px){
      width: 320px;
      height: 320px;
    }
    @media only screen and (max-width : 380px){
      width: 300px;
      height: 300px;
    }
     .inner-circle{
      box-shadow: 0 0 10px 10px #fabd44;
      filter: drop-shadow(0px 0px 3px #F3AD26);
    }
  }
  .percentage{
    position: absolute;
    top: 35%;
    left: 50%;
    transform: translateX(-50%);
    font-weight: 400;
    font-size: 89px;
    line-height: 108px;
    display: flex;
    align-items: center;
    text-align: center;
    color: #FFFFFF;
    text-shadow: 0px 0px 5px #F3AD26;
    @media only screen and (max-width : 1460px){
      top: 33%;
      font-size: 69px;
    }
    @media only screen and (max-width : 380px){
      top: 30%;
      font-size: 60px;
    }
  }
}

</style>
