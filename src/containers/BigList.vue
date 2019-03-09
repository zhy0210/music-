<template>
    <div class="BigList">
        <img src="../assets/images/hot.png" alt="">
        <!-- <img :src="list.coverUrl" alt=""> -->
        <i class="ico iconfont icon-fanhuijiantouxiangqingye" @click="$router.go(-1)"></i>
        <PlayAll />
        {{this.$route.params.topid}}
        <Sing />
        
    </div>
</template>

<script>
import  PlayAll from '../components/PlayAll'
import  Sing from '../components/Sing'
import Model from '../components/model.js'

export default {
    name:"BigList",
    data(){
        return{
          list:{},
          idx:Model[this.$route.params.topid]
        }
    },
    components:{
        PlayAll,
        Sing
    },
    mounted() {
        this.$axios.get('http://localhost:3000/top/list',{
            params:{
                idx:this.idx
            }
        }).then(res =>{
            this.list = res.data.list
            console.log(this.list)
        }).catch(res =>{
            console.log(error)
        })


        

    },
}
</script>

<style lang="less" scoped>
img{
    width: 100%;
}
.ico{
    position: absolute;
    left: 10px;
    top: 20px;
    color: white;
    font-size: 34px;
}
</style>
