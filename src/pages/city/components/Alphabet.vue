<template>
    <ul class="list">
        <li 
        class="item" 
        v-for='item of letters' 
        :key="item"
        :ref='item'
        @touchstart='handleTouchStart'
        @touchmove = "handleTouchMove"
        @touchEnd ="handleTouchEnd"
        @click='handleLetterClick'
        >{{item}}
        
        </li>
    </ul>
</template>

<script>
    export default {
        name:'CityAlphabet',
        props:{
            cities:Object
        },
        computed:{
            letters(){
                const letters = []
                for (let i in this.cities){
                    letters.push(i)
                }
                return letters
            }
        },
        updated(){
            this.startY = this.$refs['A'][0].offsetTop
        },
        data(){
            return {
                touchStatus:false,
                startY:0,
                timer:null
            }
            
        },
        methods:{
            handleLetterClick(e){

               this.$emit('change',e.target.innerText)
            },
            handleTouchStart(){
                this.touchStatus = true
            },
            handleTouchMove(e){
                if(this.touchStatus){
                    if(this.timer){
                        clearTimeout(this.timer)
                    }
                    this.timer =setTimeout(()=>{
                            // const startY = this.$refs['A'][0].offsetTop
                        const touchY = e.touches[0].clientY - 79
                        const index = Math.floor((touchY - this.startY)/20)
                        // console.log(index)
                        if(index>=0 && index< this.letters.length){
                            this.$emit('change',this.letters[index])
                        }
                    },16)
                    
                    
                }
            },
            handleTouchEnd(){
                this.touchStatus = false
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .list
        display :flex
        flex-direction :column
        justify-content :center
        position :absolute
        right :0
        top:1.58rem
        bottom:0
        width:0.4rem
        
        .item
            line-height :0.4rem
            text-align :center
            color :$bgColor
</style>