<template>
  <div class="nav">
          <h1 class="logo"><router-link to="/">crypto<span>buds</span></router-link></h1>

          <ul class="navOptions" >
            <li class="item"><router-link to="/gallery">Gallery</router-link></li>
            <li class="item"><router-link to="/mynfts" v-if="isConnected">MY NFTs</router-link></li>
          </ul>
          <button v-if="isConnected" class="connectedBtn" @click="isConnected = !isConnected">
            <img src="@/assets/connectedBtn.png" alt="">
          </button>

          <button class="connectWallet" v-else @click="isConnected = !isConnected">connect wallet</button>

          <div class="blur-box">
            <img src="@/assets/pixel.png" alt="">
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
      @media only screen and (max-width:1560px){
        padding: 30px;
      } 
      @media only screen and (max-width:380px){
        padding: 30px 15px;
      } 
      @media only screen and (max-width:1120px){
        height: min-content;
      }

      .logo{
        display: flex;
        align-items: center;
        a{
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
          @media only screen and (max-width:580px){
            font-size: 14px;
          } 
          
          span{
            color: #F3AD26;
          }
        }
      } 
      .navOptions{
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
        &>:last-child a{
          border-left: 1px solid #F3AD26;
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
            @media only screen and (max-width:580px){
              font-size: 16px;
              padding: 3px 10px;
            } 
            &:hover{
                color: #F3AD26; 
            }
          }
        }
      }
      .connectedBtn{
        position: relative;
        z-index: 2;
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
        @media only screen and (max-width:560px){
          width: 25px;
          height: 25px;
        }
        @media only screen and (max-width:370px){
          width: 20px;
          height: 20px;
        }
        img{
          width: 50px;
          height: 50px;
          @media only screen and (max-width:1560px){
            width: 25px;
            height: 25px;
          }
          @media only screen and (max-width:560px){
            width: 15px;
            height: 15px;
          }
          @media only screen and (max-width:370px){
            width: 12px;
            height: 12px;
          }
        }
      }
      .connectWallet{
        position: relative;
        z-index: 1;
        width: 233px;
        height: 67px;
        font-size: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: 400;
        color: #F3AD26;        
        background: #5B5947;
        border-radius: 98px;
        border:none;
        text-transform: uppercase;
        cursor: pointer;
        @media only screen and (max-width:1460px){
          width: 180px;
          height: 40px;
          font-size: 15px;
        }
        @media only screen and (max-width:580px){
          width: 120px;
          height: 24px;
          font-size: 10px;
        }
      }
      .blur-box{
        position: absolute;
        bottom: -1px;
        right: -1px; 
        width: min-content;
        width: 56px;
        height: 56px;
        @media only screen and (max-width:1790px){
            width: 40px;
            height: 40px;
          }
          @media only screen and (max-width:980px){
            width: 25px;
            height: 25px;
          }
        img{
          width: 100%;
          height: 100%;
        }
      }
    }
</style>