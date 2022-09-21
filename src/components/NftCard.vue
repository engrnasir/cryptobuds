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
        <div v-for="i in 4" :key="i" class="b-box" :class="`b-box${i}`"></div>
    </div>
    <div class="blur-box2">
        <div v-for="i in 4" :key="i" class="b-box" :class="`b-box${i}`"></div>
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
        margin-right: 20px;
        margin-bottom: 20px;
        transition: all .25s;
        &:hover{
          transform: scale(1.03);
        }
        .thumbnail{
            position: relative;
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
                top: 0px;
                left: 0px; 
                width: min-content;
                display: grid;
                grid-gap: 0;
                background: transparent;
        
                grid-template-columns: repeat(2, 1fr);
                .b-box{
                    width: 14px;
                    height: 14px;
                    border: none;
                    outline: none;
                }
                .b-box2,.b-box3{
                    background: #5B5947;
                }
                .b-box4{
                    background: #0F0F0F;
                }
                .b-box1{
                    border:1px solid #D9D9D9;
                    background: #D9D9D9;
                }
        }
        .blur-box2{
                position: absolute;
                bottom: 0px;
                right: 0px; 
                width: min-content;
                display: grid;
                grid-gap: 0;
                background: transparent;
        
                grid-template-columns: repeat(2, 1fr);
                .b-box{
                    width: 14px;
                    height: 14px;
                    border: none;
                    outline: none;
                }
                .b-box2,.b-box3{
                    background: #5B5947;
                }
                .b-box1{
                    background: #0F0F0F;
                }
                .b-box4{
                    border:1px solid #D9D9D9;
                    background: #D9D9D9;
                }
        }
    }

</style>