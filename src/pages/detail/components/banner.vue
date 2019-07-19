<template>
<div>
    <div class="banner" @click='handleBannerClick'>
        <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1503/1a/1a846004fed50dde.water.jpg_600x330_04abd5b6.jpg" alt="">
        <div class="banner-info">
            <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
            <div class="banner-number"> 
                <span class="iconfont banner-icon">&#xe692;</span>
                 39
             </div>    
        </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
</div>    
</template>

<script>
    import CommonGallary from 'common/gallary/Gallary'
    export default {
        name:'DetailBanner',
        data(){

            return {
                showGallary:false,
                imgs:['https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563554236021&di=c01de530a95b17b6af30e2559809bb47&imgtype=0&src=http%3A%2F%2Feasyread.ph.126.net%2FQUEqI2tXwppxKJH09QLVZg%3D%3D%2F7917031276780591419.jpg','https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563554236021&di=c01de530a95b17b6af30e2559809bb47&imgtype=0&src=http%3A%2F%2Feasyread.ph.126.net%2FQUEqI2tXwppxKJH09QLVZg%3D%3D%2F7917031276780591419.jpg']
            }

        },
        methods:{
            handleBannerClick(){
                this.showGallary = true
            },
            handleGallaryClose(){
                this.showGallary = false
            }
        },
        components:{
            CommonGallary
        }
    }
</script>

<style lang="stylus" scoped>
    .banner
        position :relative
        overflow :hidden
        height:0
        padding-bottom:55%
        .banner-img
            width :100%
        .banner-info
            display :flex
            position :absolute
            left:0
            right:0
            bottom:0
            line-height:0.6rem  
            color:#fff  
            background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8)) 
            .banner-title
                flex:1
                font-size:0.32rem
                padding:0 0.2rem
            .banner-number
                margin-top:0.2rem
                padding:0 0.4rem  
                line-height:0.32rem
                height :0.32rem  
                border-radius:0.2rem
                background :rgba(0,0,0,0,8)
                font-size:0.24rem
                .banner-icon
                    font-size:0.24rem
</style>