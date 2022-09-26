<template>
  <div class="home">
    <div class="overlay" v-if="showPopup"></div>
    <div class="popup" v-if="showPopup">
      <button class="closeBtn" @click="showPopup=false">x</button>
      <h3>TRANSACTION SENT ...</h3>
      <p>PLEASE WAIT FOR CONFORMATION</p>
    </div>
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
            <img src="@/assets/arrowdown.png" alt="" class="arrowdown">
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
            <button class="btn dercrementBtn" @click="value>0?value--:value"><p>-</p></button>
            <input type="number" class="valueInput" v-model="value">
            <span>Max</span>
            <button class="btn incrementBtn" @click="value++"><p>+</p></button>
          </div>
          <button class="mintBtn" @click="value>0?showPopup=true:''" :class="value==0? 'disableMint':''">mint</button>
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
        showPopup:false,

        value:0,
        firstVal:400,
        totalVal:1400,

        val1:1,
        val2:0.1
      }
    }
}
</script>

<style lang="scss" scoped>
  .overlay{
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
    width: 100%;
    height: 130vh;
    background: rgba(0, 0, 0, 0.15);
    backdrop-filter: blur(15px);
  }
  .popup{
    position: fixed;
    top: 20vh;
    left: 50%;
    transform: translateX(-50%);
    z-index: 999;
    width: 608px;
    height: 409px;
    background: rgba(0, 0, 0, 0.66);
    border: 7px solid #F3AD26;
    box-shadow: 0px 0px 23px #000000;
    backdrop-filter: blur(35px);
    border-radius: 14px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    @media only screen and (max-width: 1460px){   
      width: 486px;
      height: 327px;   
    }
    @media only screen and (max-width: 580px){
      width: 95%;
    }

    .closeBtn{
      color : #F3AD26;
      font-size: 40px;
      background: transparent; 
      border: none;
      cursor: pointer;
      position: absolute;
      top: 5px;
      right: 15px;
      font-weight: 300;
      @media only screen and (max-width: 580px){
        font-size: 30px;
      }
    }
    h3{
      font-weight: 400;
      font-size: 34px;
      line-height: 41px;
      color: #FFFFFF;
      @media only screen and (max-width: 1460px){
        font-size: 24px;
      }
      @media only screen and (max-width: 580px){
        font-size: 20px;
      }
    }
    p{
      width: 60%;
      font-weight: 400;
      font-size: 34px;
      line-height: 41px;
      text-align: center;
      color: #F3DF26;
      @media only screen and (max-width: 1460px){
        font-size: 24px;
      }
      @media only screen and (max-width: 580px){
        font-size: 20px;
      }
    }
  }

  .wrapper{
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-gap: 34px;
    justify-content: space-between;
    justify-items: center;
    @media only screen and (max-width:1120px){
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
        @media only screen and (max-width:580px){
          letter-spacing: 0.22em;
        }
      }
      .arrow{
        width: 450px;
        padding-bottom: 189px;
        @media only screen and (max-width:1460px){
          width: 410px;
        }
        @media only screen and (max-width:1120px){
         display: none;
        }
      }   
      .arrowdown{
        height: 86px;
        margin-left: 50%;
        transform: translateX(-50%);
        margin-top: 20px;
        @media only screen and (min-width:1120px){
         display: none;
        }

      }     
    }
  }
  .right{
    position: relative;
    width: 100%;
    margin-top: 25px;
    background: #0F0F0F;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 80px 40px;
    @media only screen and (max-width:560px){
      padding: 50px 20px;
    }
    .blur-box{
        position: absolute;
        top: -2px;
        left: -2.4px; 
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
            font-size: 18px;
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
      @media only screen and (max-width:580px){
        width: 300px;
        height: 65px;;
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
        @media only screen and (max-width:580px){
          width: 63px;
          height: 63px;
          font-size: 50px;
        }
      }
      .valueInput{
        background: transparent;
        border: none;
        text-align: right;
        width: 100px;
        font-size: 40px;
        color: #fff;
        padding: 5px 2px; 
        outline: none;
        @media only screen and (max-width:1120px){
          width: 80px;
          font-size: 30px;
        }
        @media only screen and (max-width:580px){
          padding:2px; 
          font-size: 20px;
        }
      }
      span{  
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
    .mintBtn{
      background: #F3AD26;
      box-shadow: 0px 0px 17px #F3AD26;
      border-radius: 81px;
      width: 447px;
      height: 80px;
      border: none;
      margin: 28px auto;

      font-weight: 400;
      font-size: 36px;
      color: #1A1919;
      text-transform: uppercase;
      cursor: pointer;
      transition: all .2s;
      &:hover, &a:active{
        box-shadow: 0px 0px 5px #F3AD26;
      }
      @media only screen and (max-width:580px){
        width: 300px;
        height: 65px;
        font-size: 28px;
      }


    }
    .disableMint{
      background: #4B4230;
      box-shadow: none;
      color: #353535;
      &:hover, &a:active{
        box-shadow: none;
      }
    }
    .currencies{
      color: #fff;
      font-weight: 400;
      font-size: 40px;
      display: flex;
      text-transform: uppercase;
      @media only screen and (max-width:580px){
        font-size: 28px;
        width: 320px;
      }
      .secondCurrency,
      .firstCurrency{
        width: 230px;
        text-align: center;
        padding: 10px 0;
        @media only screen and (max-width:580px){
          width:50%;
        }
      }
      .firstCurrency{
        border-right: 1px solid #F3AD26;
      }
    }

  }
</style>