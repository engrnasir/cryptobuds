<template>
  <div class="nav">
          <h1 class="logo"><router-link to="/">crypto<span>buds</span></router-link></h1>

          <ul class="navOptions" v-if="isConnected">
            <li class="item"><router-link to="/gallery">Gallery</router-link></li>
            <li class="item"><router-link to="/mynfts">MY NFTs</router-link></li>
          </ul>
          <button v-if="isConnected" class="connectedBtn" @click="isConnected = !isConnected">
            <img src="@/assets/connectedBtn.png" alt="">
          </button>

          <button class="connectWallet" v-else @click="isConnected = !isConnected">connect wallet</button>

          <div class="blur-box">
            <div v-for="i in 16" :key="i" class="box" :class="`box${i}`"></div>
          </div>
        </div>
</template>

<script>
export default {
    data(){
        return{
            isConnected:true,
        }
    }
}
</script>

<style lang="scss" scoped>
.nav{
      outline: none;
      position: relative;
      padding: 70px 80px;
      background-color: #0F0F0F;
      display: flex;
      align-items: center;
      justify-content: space-between;

      @media only screen and (max-width:1790px){
        padding: 50px;
      } 
      @media only screen and (max-width:1560px){
        padding-left: 30px;
      } 

      .logo a{
        text-decoration: none;
        font-weight: 400;
        font-size: 30px;
        text-transform: uppercase;
        color: #fff;
        @media only screen and (max-width:1560px){
          font-size: 28px;
        }
        @media only screen and (max-width:1180px){
          font-size: 24px;
        } 
        @media only screen and (max-width:520px){
          font-size: 20px;
        } 
        span{
          color: #F3AD26;
        }
      }
      .navOptions{
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
        &>:first-child a{
          border-right: 1px solid #F3AD26;
        }
        .item{
          a{
            text-decoration: none;
            color: #fff;
            font-weight: 400;
            font-size: 30px;
            padding: 10px 30px;
            @media only screen and (max-width:1790px){
              font-size: 24px;
            }
            @media only screen and (max-width:1460px){
              padding: 10px 15px;
            }
            @media only screen and (max-width:1180px){
              font-size: 20px;
            } 
            @media only screen and (max-width:520px){
              font-size: 14px;
              padding: 5px 10px;
            } 
            &:hover{
                color: #F3AD26; 
            }
          }
        }
      }
      .connectedBtn{
        width: 60px;
        height: 60px;
        background: #F3AD26;
        border-radius: 98px;
        display: flex;
        align-items: center;
        justify-content: center;
        filter: drop-shadow(0px 0px 17px #F3AD26);
        border: none;
        cursor: pointer; 
        @media only screen and (max-width:1790px){
          width: 60px;
          height: 60px;
          filter: drop-shadow(0px 0px 10px #F3AD26);
        }
        @media only screen and (max-width:1560px){
          width: 35px;
          height: 35px;
        }
        img{
          width: 50px;
          height: 50px;
          @media only screen and (max-width:1560px){
            width: 25px;
            height: 25px;
          }
        }
      }
      .connectWallet{
        width: 320px;
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: 400;
        font-size: 24px;
        color: #F3AD26;        
        background: #5B5947;
        border-radius: 98px;
        border:none;
        text-transform: uppercase;
        cursor: pointer;
        @media only screen and (max-width:1790px){
          width: 233px;
          height: 67px;
          font-size: 20px;
        }
      }
      .blur-box{
        position: absolute;
        bottom: -1px;
        right: -2px; 
        width: min-content;
        width: 56px;
        display: flex;
        flex-wrap: wrap;
        background: #D9D9D9;
        grid-template-columns: repeat(4, 1fr);
        @media only screen and (max-width:1790px){
            width: 40px;
          }
        .box{
          width: 14px;
          height: 14px;
          border: none;
          outline: none;
          @media only screen and (max-width:1790px){
            width: 10px;
            height: 10px;
          }
        }
        .box1,.box2,.box5{
          background-color: #0F0F0F;
          border: 2px solid #0F0F0F;;
        }
        .box3,.box6,.box9{
          background: #5B5947;
        }
        .box4, .box7, .box8,.box10, .box11, .box12, .box13,.box14, .box15,
        .box16{
          border:1px solid #D9D9D9;
          background: #D9D9D9;
        }
      }
    }
</style>