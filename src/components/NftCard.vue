<template>
  <div class="card-container">
    <div class="thumbnail">
        <img :src="require(`@/assets/${info.img}`)" alt="">
        <div class="box box1"></div>
        <div class="box box2"></div>
    </div>
    <div class="number">
        <h3 class="text">number</h3>
        <p class="value">{{info.number}}</p>
    </div>
    <div class="rank">
        <h3 class="text">ranked</h3>
        <p class="value">{{info.ranked}}</p>
    </div>
    <div class="blur-box1">
        <img src="@/assets/nftPixelup.png" alt="">
    </div>
    <div class="blur-box2">
        <img src="@/assets/nftPixeldown.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
    props:['info'],
}
</script>

<style lang="scss" scoped>
    .card-container{
        position: relative;
        padding: 28px;
        padding-bottom: 42px;
        background: #0F0F0F;
        margin: 10px;
        margin-bottom: 20px;
        transition: all .25s;
        width: 240px;
        min-width: 240px;
        &:hover{
          cursor: pointer;
        }
        .thumbnail{
            position: relative;
            z-index: 2;
            display: flex;
            align-items: center;
            justify-content: center;
            img{
                width: 174px;
                height: 174px;
                outline: 5px solid #F3AD26;
                padding: 3px;
            }
            .box{
                width: 8px;
                height: 8px;
                position: absolute;
                background: #0F0F0F;

            }
            .box1{
                top: -6px;
                left: -2px;
            }
            .box2{
                right: -2px;
                bottom: -6px;
            }
        }
        .rank,
        .number{
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: 26px;
            width: 184px;
            text-transform: uppercase;
            .text{
                font-weight: 400;
                font-size: 20px;
                color: #F3AD26;
            }
            .value{
                font-weight: 400;
                font-size: 34px;
                color: #FFFFFF;
            }
        }
        .blur-box1{
            position: absolute;
            top: -3px;
            left: -2px; 
            width: 28px;
            height: 28px;
            img{
                width: 100%;
                height: 100%;
            }   
        }
        .blur-box2{
            position: absolute;
            bottom: -1px;
            right: -1px; 
            width: 28px;
            height: 28px;
            img{
                width: 100%;
                height: 100%;
            } 
        }
    }

</style>