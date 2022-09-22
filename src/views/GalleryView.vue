<template>
    <div class="container">
      <div class="row wrapper">
        <div class="left">
          <Navbar/>
          <div class="content">
            <h2 class="the">the</h2>
            <p class="gallery">GALLERY</p>
          </div>
        </div>
        <div class="right">
            <div class="filterBar">
                <input type="text" placeholder="SEARCH FOR #ID">
                <div class="sortingWrapper" :class="showSortingOptions? '':'hideOptions'">
                  <div class="sorting" @click="showSortingOptions=!showSortingOptions">no sorting</div>
                  <ul class="options">
                    <li class="option">option1</li>
                    <li class="option">option2</li>
                    <li class="option">option3</li>
                    <li class="option">option4</li>
                  </ul>
                </div>
                <div class="blur-box">
                    <!-- <div v-for="i in 4" :key="i" class="box" :class="`box${i}`"></div> -->
                    <img src="@/assets/filterPixel.png" alt="">
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
import Navbar from "../components/Navbar.vue";
import NftCard from "@/components/NftCard.vue";
  export default {
      components: { Navbar, NftCard },
      data(){
        return{
          showSortingOptions:false,
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
            {img:'nft5.png', number:54, ranked:4500},
            {img:'nft6.png', number:54, ranked:4500},
            {img:'nft7.png', number:54, ranked:4500},
            {img:'nft8.png', number:54, ranked:4500},
            {img:'nft9.png', number:54, ranked:4500},
          ]
        }
      }
  }
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/style.scss';
  </style>