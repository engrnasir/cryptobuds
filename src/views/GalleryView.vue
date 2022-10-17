<template>
    <div class="container">
      <button class="goTop" v-if="showScroll" @click="goTop">Go Top</button>
      <div class="row wrapper">
        <div class="overlay" v-if="showSortingOptions" @click="showSortingOptions=false"></div>
        <div class="left">
          <Navbar/>
          <div class="content">
            <h2 class="the">the</h2>
            <p class="gallery">GALLERY</p>
          </div>
        </div>
        <div class="right">
            <div class="filterBar">
              <label for="idInput" class="searchInput">
                <input type="text" placeholder="SEARCH FOR #ID" id="idInput">
                <button class="searchButton">
                  <svg width="33" height="25" viewBox="0 0 33 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <circle cx="12" cy="12" r="9.5" stroke="#b9b592" stroke-width="3"/>
                  <line x1="21.0125" y1="18.3292" x2="27.3293" y2="21.4876" stroke="#b9b592" stroke-width="3" stroke-linecap="round"/>
                  </svg>
                </button>
              </label>
                <div class="sortingWrapper" :class="showSortingOptions? '':'hideOptions'">
                  <div class="sorting" @click.stop="showSortingOptions=!showSortingOptions">no sorting</div>
                  <ul class="options">
                    <li class="option" v-for="(option, index) in options" :key="index" @click="showSortingOptions=false">{{option}}</li>
                  </ul>
                </div>
                <div class="blur-box">
                    <img src="@/assets/filterPixel.png" alt="">
                </div>
            </div>
            <div class="cards" id="nft-gallery-cards">
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
          showScroll : false,
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
          ],
          options:['option1', 'option2', 'option3', 'option4']
        }
      },
      methods:{
        goTop(){
          document.getElementById('nft-gallery-cards').scrollTo(0, 0);
        },
        setShowScroll(){
          var doc = document.getElementById('nft-gallery-cards');
          var top = (doc.scrollTop) - (doc.clientTop || 0);
          this.showScroll = top>0;
        }
    },
    mounted () {
      document.getElementById('nft-gallery-cards').addEventListener('scroll', this.setShowScroll);
    },
  }
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/style.scss';
  </style>