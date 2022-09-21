<template>
    <div class="my-nft">
      <div class="row wrapper">
        <div class="left">
          <Navbar/>
          <div class="content">
            <h2 class="the">my</h2>
            <p class="gallery">nfts</p>
          </div>
        </div>
        <div class="right">
            <div class="filterBar">
                <input type="text" placeholder="SEARCH FOR #ID">
                <div class="sorting">no sorting</div>
                <div class="blur-box">
                    <div v-for="i in 4" :key="i" class="box" :class="`box${i}`"></div>
                </div>
            </div>
            <div class="cards">
              <NftCard v-for="(card,index) in cards" :key="index" :info="card" />
            </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import ProgressComp from "../components/ProgressComp.vue";
  import Navbar from "../components/Navbar.vue";
import NftCard from "@/components/NftCard.vue";
  export default {
      components: { ProgressComp, Navbar, NftCard },
      data(){
        return{
          value:1,
          firstVal:400,
          totalVal:1400,
  
          val1:1,
          val2:0.1,
          cards:[
            {img:'nft1.png', number:54, ranked:4500},
            {img:'nft2.png', number:54, ranked:4500},
            {img:'nft3.png', number:54, ranked:4500},
            {img:'nft4.png', number:54, ranked:4500},
          ]
        }
      }
  }
  </script>
  
  <style lang="scss" scoped>
    .my-nft{
        max-height: 100vh;
    }
    .wrapper{
        position: relative;
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
        min-height: 80vh;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        border-right: 13px solid #0F0F0F;
        @media only screen and (max-width:1120px){
          min-height: 30vh;
          border-right: 10px solid #0F0F0F;
        }
        .gallery,
        .the{
            font-weight: 500;
            font-size: 81px;
            letter-spacing: 0.14em;
            color: #000000;
            text-transform: uppercase;
            @media only screen and (max-width:1660px){
              font-size: 61px;
            }
            @media only screen and (max-width:1460px){
              font-size: 41px;
            }
        }
        .gallery{
            font-weight: 200;
            font-size: 107px;
            letter-spacing: 0.34em;
            color: #000000;
            @media only screen and (max-width:1660px){
              font-size: 87px;
            }
            @media only screen and (max-width:1460px){
              font-size: 67px;
              letter-spacing: 0.24em;
            }
        }      
      }
    }
    .right{
      position: relative;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
        
      .filterBar{
        position: relative;
        width: 100%;
        height: 90px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 18px 45px;
        background: #0F0F0F;
        margin-bottom: 40px;
        @media only screen and (max-width:1120px){
          position: sticky;
          top: 0;
          z-index: 99;
        }
        input[type='text']{
            width: 485px;
            height: 49px;
            border: 7px solid #5B5947;
            font-weight: 400;
            font-size: 15px;
            color: #6A6A6A;
            background: transparent;
            padding: 10px;
            @media only screen and (max-width:1720px){
              width: 50%;
            }
        }
        .sorting{
            width: 240px;
            height: 49px;
            border: 2px solid #F3AD26;
            border-radius: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 400;
            font-size: 15px;
            color: #F3AD26;
            text-transform: uppercase;
            @media only screen and (max-width: 1360px){
              width: 180px;
              height: 39px;
            }
        }
        .blur-box{
          position: absolute;
          bottom: 0px;
          left: 0px; 
          width: min-content;
          display: grid;
          grid-gap: 0;
          background: transparent;
  
          grid-template-columns: repeat(2, 1fr);
          .box{
            width: 14px;
            height: 14px;
            border: none;
            outline: none;
          }
          .box1,.box4{
            background: #5B5947;
          }
          .box2{
            background: #0F0F0F;
          }
          .box3{
            border:1px solid #D9D9D9;
            background: #D9D9D9;
          }
      }
      }
      .cards{
        width: 100%;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        max-height: 90vh;
        overflow-y: scroll;
        @media only screen and (max-width:1460px){
          justify-content: space-evenly;
        }
        &::-webkit-scrollbar {
            width: 10px;
        }
        &::-webkit-scrollbar-track{
            background: transparent;
        }
        &::-webkit-scrollbar-thumb{
            background: #0F0F0F;
        }
        &::-webkit-scrollbar-thumb:hover{
            background: #303030;
        }
      }
  
    }
  </style>