<template>
    <div class="wrapper">
         <swiper :options="swiperOption" v-if="showSwiper">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key='item.id'>
                <img class="swiper-img" :src="item.imgUrl">
            </swiper-slide>
            
            
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
            
        </swiper>
    </div>
</template>

<script>
    export default {
       name:'HomeSwiper',
       props:{
           list:Array
       },
       data(){
           return {
               swiperOption:{
                   pagination:'.swiper-pagination',
                   loop:1000,
                   autoplay:1000
               },
               swiperList:[{
                   id:'0001',
                   imgUrl:"https://aecpm.alicdn.com/simba/img/TB1CWf9KpXXXXbuXpXXSutbFXXX.jpg_q50.jpg"
               },{
                   id:'0002',
                   imgUrl:"https://aecpm.alicdn.com/simba/img/TB14ab1KpXXXXclXFXXSutbFXXX.jpg_q50.jpg"
               }]
           }
       } ,
       computed:{
           showSwiper(){
               return this.list.length
           }
       }
    }
</script>

<style lang='stylus' scoped>

.wrapper >>> .swiper-pagination-bullet-active
    background :white !important    

.wrapper
    overflow :hidden
    width:100%
    height:0
    padding-bottom:31.25%
    background :#eee
    .swiper-img
        width:100%   

</style>