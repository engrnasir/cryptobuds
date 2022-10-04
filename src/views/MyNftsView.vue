<template>
    <div class="container">
      <div class="row wrapper">
        <div class="overlay" v-if="showSortingOptions" @click="showSortingOptions=false"></div>
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
                <div class="sortingWrapper" :class="showSortingOptions? '':'hideOptions'">
                  <div class="sorting">
                    <div class="minusBtn"><span>-</span></div>
                    <span @click="showSortingOptions=!showSortingOptions"> no sorting</span>
                    <div class="addBtn"><span>+</span></div>
                  </div>
                  <ul class="options" v-if="showSortingOptions">
                    <li class="option" v-for="(option, index) in options" :key="index" @click="showSortingOptions=false">{{option}}</li>
                  </ul>
                </div>
                <div class="blur-box">
                    <img src="@/assets/filterPixel.png" alt="">
                </div>
            </div>
            <div class="cards">
              <NftCard v-for="(card,index) in cards" :key="index" :info="card" />
              <h2 class="no-nft" v-if="cards.length<=0">You have no NFT in your wallet</h2>
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
          showSortingOptions:false,
          value:1,
          firstVal:400,
          totalVal:1400,
  
          val1:1,
          val2:0.1,
          cards:[
            // {img:'nft1.png', number:54, ranked:4500},
            // {img:'nft2.png', number:54, ranked:4500},
            // {img:'nft3.png', number:54, ranked:4500},
            // {img:'nft4.png', number:54, ranked:4500},
          ],
          options:[
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
            'option1', 'option2', 'option3', 'option4',
        ]
        }
      }
  }
  </script>
  
  <style lang="scss" scoped>
    @import '@/assets/style.scss';
  </style>