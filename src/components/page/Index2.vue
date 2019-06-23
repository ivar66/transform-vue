<template>
    <el-container>
        <el-header> <top-nav></top-nav></el-header>
        <el-main>
            <template>
                <el-carousel indicator-position="outside">
                    <el-carousel-item v-for="item in 1" :key="item">
                        <div class="scoll-div">
                            <a href="http://baidu.com">
                                <img :src="'http://blog.lovecathy.cn/image/show/articles-2019-06-zuuta6p55d0e34364f61a.png'" class="scoll-img">
                            </a>
                        </div>
                        <!--<h3>{{ item }}</h3>-->
                    </el-carousel-item>
                </el-carousel>
            </template>

        </el-main>
        <el-footer><footer-nav></footer-nav></el-footer>
    </el-container>
</template>

<script>
    import TopNav from '@/components/common/TopNav'
    import FooterNav from '@/components/common/FooterNav'

    export default {
        name: "Index2",
        components:{
            TopNav,
            FooterNav,
        },

    }

</script>

<style scoped>
    .el-header{
        padding: 0;
    }
    .el-main {
        width: 1000px;
        min-height: 800px;
        margin: 0 auto;
    }
    .el-carousel__item .scoll-div{
         height: 300px;
    }
    .el-carousel__item .scoll-div a{
        height: 300px;
    }
    .el-carousel__item .scoll-div a .scoll-img{
        height: 300px;
    }
    .el-carousel__item:nth-child(2n) {
        background-color: #99a9bf;
    }
    .el-carousel__item:nth-child(2n+1) {
        background-color: #d3dce6;
    }
</style>