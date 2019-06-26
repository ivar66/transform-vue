<template>
    <el-container>
        <el-header> <top-nav></top-nav></el-header>
        <el-main>
            <el-carousel indicator-position="outside">
                <el-carousel-item v-for="(item,index) in banner_list" :key="index">
                    <div class="scoll-div">
                        <a :href = "item.banner_url">
                            <img :src="'http://blog.lovecathy.cn/image/show/'+ item.banner_pic_url" class="scoll-img">
                        </a>
                    </div>
                </el-carousel-item>
            </el-carousel>
            <div class="content">
                <div class="content-left">
                    <el-divider content-position="left">最新文章</el-divider>
                    <!--以下为列表页-->
                    <el-card class="box-card content-left-card" v-for="(item,index) in list" :key="index" :id="item.id" v-loading="loading"
                             element-loading-text="拼命加载中"
                             element-loading-spinner="el-icon-loading"
                             element-loading-background="rgba(0, 0, 0, 0.5)">
                        <div class="card-header">
                            <span class="title"><a :href = "'blog/'+ item.id + '/detail'" class="article-title" >{{item.title | ellipsis}}</a></span>
                            <span class="timer">{{item.created_at}}</span>
                        </div>
                        <div class="card-content">
                            <span>{{item.summary}}</span>
                        </div>
                        <div class="card-footer">
                            <span>{{item.user_name}}</span>
                            <el-divider direction="vertical"></el-divider>
                            <span class="tag">{{item.category_name}}</span>
                        </div>
                    </el-card>
                    <div class="load-more" v-on:click="onLoad" v-if="has_more"><span>加载更多...</span></div>
                </div>
                <div class="content-right">
                    <el-card class="box-card content-right-card">
                        <div class="right-header">
                            <img src="https://avatar-static.segmentfault.com/977/959/977959162-5a59cf9e1d814_huge256" alt="">
                            <!--<img src="https://blog.iwaterlc.com/static/media/avatar.1fc774ca.jpg" alt="">-->
                        </div>
                        <div class="right-content">
                            <div class="name"><span>October</span></div>
                            <div class="feature"><span>后端打杂人员，代码洁癖，业余摄影</span></div>
                        </div>
                    </el-card>
                </div>
            </div>
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
                'banner_list':[],
                list: [],    //存放数据容器
                page: 0,    //第一条数据
                number: 5,    //第五条数据
                has_more:false,
                loading:true, // 是否显示loading
            }
        },
        name: "Index2",
        filters: {
            ellipsis (value) {
                if (!value) return '';
                if (value.length > 32) {
                    return value.slice(0,32) + '...'
                }
                return value
            }
        },
        components:{
            TopNav,
            FooterNav,
        },
        created(){
            axios.get('http://blog.lovecathy.cn/api/banner/banner_lists')
                .then(response=>{
                    // console.log(response);
                    this.banner_list = response.data.data
                })
                .catch(error=>{
                    console.log(error);
                    alert('网络错误，不能访问');
                });
            axios.get('http://blog.lovecathy.cn/api/article/new_articles')
                .then((res) => {
                    this.list = res.data.data;
                    this.has_more = true;
                    this.loading = false;
                })
                .catch((error) => {
                    console.log(error);
                });
        },
        //点击加载更多
        methods: {
            onLoad(){
                this.has_more = false;
                //累加5条数据
                this.page = this.page + 5;
                this.number = this.number + 5;
                // 截取后返回的是一个数组对象
                axios.get('http://blog.lovecathy.cn/api/article/new_articles')
                    .then((res) => {
                        let data = res.data.data;
                        data.forEach((item, index) => {
                            //因此只需要遍历里面的对象 因为数组push不进数组 push对象到数组里即可
                            console.log('item' + item);
                            this.list.push(item);
                        });
                        this.has_more = true;
                    })
                    .catch((error) => {
                        console.log(error);
                    });
            }
        }
    }

</script>

<style scoped>
    .el-container{
        background:#f0f2f5 ;
    }
    .el-header,.el-footer{
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
    .content{
        display: flex;
        flex-direction: row;
    }
    .content-left{
        width: 600px;
    }
    .content-left-card{
        width: 600px;
        margin-bottom: 10px;
    }
    .box-card .card-header{
        display: flex;
        justify-content: space-between;
    }
    .box-card .card-header .title a{
        font-size: 1.2rem;
        font-weight: 600;
        line-height: 1.2;
        color: #2e3135;
        text-decoration: none;
    }
    .box-card .card-header .timer{
        color: rgba(0,0,0,.45);
        font-size: 14px;
        line-height: 22px;
    }
    .box-card .card-content{
        color: rgba(0,0,0,.45);
        font-size: 14px;
        line-height: 22px;
        margin-bottom: 20px;
        margin-top: 15px;
    }
    .box-card .card-footer span{
        font-size: 12px;
        /*line-height: 10px;*/
        /*display: flex;*/
        /*justify-content: space-between;*/
    }
    .box-card .card-footer .tag{
        color: #fa8c16;
        background: #fff7e6;
        border-color: #ffd591;
    }
    .load-more{
        /*使的span标签剧中*/
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        height: 30px;

        /*text-align: center;*/
        border: 1px solid #EBEEF5;
        background-color: #FFF;
    }
    .load-more:hover{
        cursor:hand;
        background:#0081cb;
    }
    .content-right{
        margin-left: 20px;
    }
    .content-right-card{
        width: 350px;
        /*height: 300px;*/
        margin-top: 50px;
        /*display: flex;*/
        /*flex-direction: row;*/
        /*justify-content: center;*/
        /*align-items: center;*/
    }
    .content-right-card .right-header{
        display: flex;
        /*flex-direction: row;*/
        justify-content: center;
        align-items: center;
    }
    .content-right-card .right-header img{
        width: 150px;
        height: 150px;
        max-width: 100%;
        border-radius: 50%;
        /*margin: 0 auto;*/
    }
    .content-right-card .right-content{
        margin-top: 20px;
    }
    .content-right-card .right-content .name,.feature{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .content-right-card .right-content .feature{

    }
    .content-right-card .right-content .name{
        font-size: 1.2rem;
        font-weight: 600;
        line-height: 1.2;
        color: #2e3135;
        margin-bottom: 15px;
    }

</style>
<!--加载更多 查看https://www.jianshu.com/p/f2dd4a35da13-->