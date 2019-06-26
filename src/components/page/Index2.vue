<template>
    <el-container>
        <el-header> <top-nav></top-nav></el-header>
        <el-main>
            <template>
                <el-carousel indicator-position="outside">
                    <el-carousel-item v-for="(item,index) in banner_list" :key="index">
                        <div class="scoll-div">
                            <a :href = "item.banner_url">
                                <img :src="'http://blog.lovecathy.cn/image/show/'+ item.banner_pic_url" class="scoll-img">
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
    import axios from 'axios'

    export default {
        data(){
            return {
                'banner_list':[]
            }
        },
        name: "Index2",
        components:{
            TopNav,
            FooterNav,
        },
        created(){
            axios.get('http://blog.lovecathy.cn/api/banner/banner_lists')
                .then(response=>{
                    console.log(response);
                    this.banner_list = response.data.data
                })
                .catch(error=>{
                    console.log(error);
                    alert('网络错误，不能访问');
                });
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