<template>
  <div class="home">
    <div class="row wrapper">
      <div class="left">
        <Navbar/>
        <div class="content">
          <h2 class="mint">
            mint <span>and</span> sell
          </h2>
          <h2 class="crypto">crypto</h2>
          <p class="buds">buds</p>
          <div class="mintNow">
            <h3 class="text">mint now</h3>
            <img src="@/assets/arrow.png" alt="" class="arrow">
          </div>
        </div>
      </div>
      <div class="right">
          <div class="blur-box">
            <img src="@/assets/rightPixel.png" alt="">
            <div v-for="i in 9" :key="i" class="box" :class="`box${i}`"></div>
          </div>
           <ProgressComp :firstVal="firstVal" :totalVal="totalVal"/>  
          <div class="values-wrapper">
            <div class="h-line"></div>
            <div class="values">
              <h3>{{firstVal}}  of  {{totalVal}}</h3>
              <p>minted</p>
            </div>
            <div class="h-line"></div>
          </div>
          <div class="range-wrapper">
            <button class="btn dercrementBtn" @click="value--"><p>-</p></button>
            <p class="value">{{value}}</p>
            <span>Max</span>
            <button class="btn incrementBtn" @click="value++"><p>+</p></button>
          </div>
          <div class="currencies">
            <p class="firstCurrency">{{val1}} nft</p>
            <p class="secondCurrency">{{val2}} eth</p>
          </div>

      </div>
    </div>
  </div>
</template>

<script>
import ProgressComp from "../components/ProgressComp.vue";
import Navbar from "../components/Navbar.vue";
export default {
    components: { ProgressComp, Navbar },
    data(){
      return{
        value:1,
        firstVal:400,
        totalVal:1400,

        val1:1,
        val2:0.1
      }
    }
}
</script>

<style lang="scss" scoped>
  .wrapper{
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-gap: 34px;
    justify-content: space-between;
    justify-items: center;
    @media only screen and (max-width:980px){
      grid-template-columns: repeat(1,1fr);
    }
  }
  .left{
    width: 100%;
    .content{
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      .mint{
        font-weight: 500;
        font-size: 48px;
        color: #000000;
        padding: 80px 0;
        text-transform: uppercase;
        span{
          font-weight: 200;
        }
        @media only screen and (max-width:980px){
          font-size: 32px;
          padding: 40px 0;
        }
      }
      .buds,
      .crypto{
        font-weight: 500;
        font-size: 80px;
        text-transform: uppercase;
        letter-spacing: 0.15em;
        @media only screen and (max-width:980px){
          font-size: 50px;
        }
      }
      .buds{
        font-weight: 200;
        letter-spacing: 0.675em;
        margin-left: 0.5em;
      }
      .mintNow{
        font-weight: 500;
        font-size: 48px;
        letter-spacing: 0.345em;
        color: #000000;
        text-shadow: 0px 0px 9px #F3AD26;
        padding: 60px 0;
        padding-bottom: 0;
        text-transform: uppercase;
        @media only screen and (max-width:1460px){
          font-size: 44px;
        }
        @media only screen and (max-width:980px){
          font-size: 32px;
        }
      }
      .arrow{
        width: 450px;
        padding-bottom: 189px;
        @media only screen and (max-width:1460px){
          width: 410px;
        }
        @media only screen and (max-width:1120px){
          padding-bottom: 120px;
        }
        @media only screen and (max-width:980px){
          width: 300px;
          padding-bottom: 80px;
        }
      }        
    }
  }
  .right{
    @media only screen and (max-width:980px){
      padding: 80px 40px;
    }
    @media only screen and (max-width:560px){
      padding: 50px 20px;
    }
    position: relative;
    width: 100%;
    margin-top: 25px;
    background: #0F0F0F;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    .blur-box{
        position: absolute;
        top: -1px;
        left: 0px; 
        width: 42px;
        height: 42px;

        @media only screen and (max-width:1460px){
          width: 30px;
          height: 30px;
        }
        img{
          width: 100%;
          height: 100%;
        }
    }
    .values-wrapper{
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      .h-line{
        width: 100%;
        height: 5px;
        background: #F3AD26;
        @media only screen and (max-width:560px){
            height: 2.5px;
          }
      }
      .values{
        padding: 100px 40px;
        @media only screen and (max-width:1460px){
          padding: 60px 30px;
        }
        @media only screen and (max-width:560px){
          padding: 30px 20px;
        }
        h3{
          font-weight: 400;
          font-size: 28px;
          line-height: 34px;
          color: #FFFFFF;
          width: max-content;
          @media only screen and (max-width:560px){
            font-size: 20px;
          }
        }
        p{
          font-weight: 400;
          font-size: 19px;
          color: #F3AD26;
          text-align: center;
          text-transform: uppercase;
          @media only screen and (max-width:560px){
            font-size: 15px;
          }
        }
      }
    }
    .range-wrapper{
      width: 447px;
      height: 93px;
      background: #5B5947;
      border-radius: 56px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-weight: 400;
      font-size: 40px;
      color: #FFFFFF;
      @media only screen and (max-width:1460px){
        width: 347px;
        height: 63px;
      }
      @media only screen and (max-width:560px){
        width: 230px;
        height: 30px;
        font-size: 20px;
      }
      .btn{
        width: 93px;
        height: 93px;
        background: #F3AD26;
        border-radius: 56px;
        border: none;
        font-weight: 400;
        font-size: 91px;
        display: flex;        
        align-items: center;
        justify-content: center;
        color: #5B5947;
        cursor: pointer;
        @media only screen and (max-width:1460px){
          width: 63px;
          height: 63px;
          font-size: 50px;
        }
        @media only screen and (max-width:560px){
          width: 30px;
          height: 30px;
          font-size: 30px;
        }
      }
      .value, span{
        margin-right: -60px;  
        @media only screen and (max-width:560px){
          font-size: 20px;
        }
      }
    }
    span{
      font-weight: 400;
      font-size: 23px;
      color: #F3AD26;
      text-transform: uppercase;
    }
    .currencies{
      color: #fff;
      margin-top: 45px;
      font-weight: 400;
      font-size: 40px;
      display: flex;
      text-transform: uppercase;
      @media only screen and (max-width:1460px){
        margin-top: 30px;
      }
      @media only screen and (max-width:580px){
        font-size: 32px;
      }
      .secondCurrency,
      .firstCurrency{
        width: 235px;
        text-align: center;
        padding: 10px 0;
        @media only screen and (max-width:580px){
          width:140px;
        }
      }
      .firstCurrency{
        border-right: 1px solid #F3AD26;
      }
    }

  }
</style>