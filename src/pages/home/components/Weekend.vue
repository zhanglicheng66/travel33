<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img"  :src='item.imgUrl'  alt="">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                   
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name:'HomeWeekend',
        props:{
            list:Array
        },
        data(){
            return {
                recommendList:[{
                id:'001',
                imgUrl:'https://imgs.qunarzz.com/piao/fusion/1707/6a/ef538175bc41a802.jpg',
                title:'日本樱花季',
                desc:'美丽的日本风情樱花飞落 大雪纷飞 飞天新地'
            },{
                id:'002',
                imgUrl:'https://imgs.qunarzz.com/piao/fusion/1707/6a/ef538175bc41a802.jpg',
                title:'日本樱花季',
                desc:'美丽的日本风情樱花飞落 大雪纷飞 飞天新地'
            },{
                id:'003',
                imgUrl:'https://imgs.qunarzz.com/piao/fusion/1707/6a/ef538175bc41a802.jpg',
                title:'日本樱花季',
                desc:'美丽的日本风情樱花飞落 大雪纷飞 飞天新地'
            }]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl' 
    @import '~@/assets/styles/mixins.styl'
        .title
           
            line-height:0.8rem 
            background:#eee
            text-indent:0.2rem
        .item-img-wrapper
            overflow:hidden
            height :0
            padding-bottom:37%
            .item-img
                width:100%
    
        .item-info
              
            padding:0.1rem
            
            .item-title
                line-height:0.54rem
                font-size:0.32rem
                color:'black'
                ellipsis()
            .item-desc
                line-height:0.4rem
                
                ellipsis()
           
</style>