<template>
    <div class="article_detail">
        <el-container>
            <el-header> <top-nav></top-nav></el-header>
            <el-main>

                <el-card class="article_detail" v-loading="loading"
                         element-loading-text="拼命加载中"
                         element-loading-spinner="el-icon-loading"
                         element-loading-background="rgba(0, 0, 0, 0.5)">
                    <div class="originalImg">
                    </div>
                    <!--标题-->
                    <div class="detail-title-wrap">
                        <h1 class="detail-title">
                            <span class="js_title">
                                {{articleDetail.title}}
                            </span>
                        </h1>
                        <div class="dc-profile clearfix">
                            <div class="l">
                                <span class="spacer">{{ articleDetail.created_at }}</span>
                                <span class="spacer spacer-2">{{ articleDetail.views }}浏览</span>
                            </div>
                        </div>
                    </div>
                    <!--正文-->
                    <div class="detail-content-wrap">
                        <div class="detail-content js-lookimg long-content">
                            <p v-html = "articleDetail.content"></p>
                        </div>
                        <!--<input name="head">-->

                        <!--</input>-->
                    </div>
                </el-card>
            </el-main>
            <el-footer><footer-nav></footer-nav></el-footer>
        </el-container>
    </div>
</template>

<script>
    import TopNav from '@/components/common/TopNav'
    import FooterNav from '@/components/common/FooterNav'
    import axios from 'axios'

    export default {
        data(){
            return{
                'articleDetail' : [],
                'loading' :true
            }
        },
        name:'article_detail',
        components:{
            TopNav,
            FooterNav,
        },
        created(){
            console.log(this.$route.params);
            if (!this.$route.params.id){
                alert('网络错误，不能访问');
            }
            var RequestUrl = 'http://blog.lovecathy.cn/api/article/'+ this.$route.params.id +'/detail'
            axios.get(RequestUrl)
                .then(response=>{
                    this.articleDetail = response.data.data;
                    this.loading = false;
                    console.log(this.articleDetail);
                })
                .catch(error=>{
                    console.log(error);
                    alert('网络错误，不能访问');
                });
        },
        // mounted () {
        //     this.init()
        // },
        // methods: {
        //     init: function () {
        //         let url = 'https://cdnjs.cloudflare.com/ajax/libs/social-share.js/1.0.16/js/social-share.min.js'
        //         let script = document.createElement('script')
        //         script.setAttribute('src', url)
        //         document.getElementsByTagName('head')[0].appendChild(script)
        //     }
        // }
    }
</script>

<style scoped>
.el-header{
    padding:0;
}
.el-main{
    margin: 10px 100px;
    min-height: 800px;
}
.el-card{
    margin: 0px 80px;
    min-height: 700px;
    width: 780px;
}
.originalImg{
    background: url('../../assets/original.png');
    background-position: 0 0;
    background-size: 64px;
    width: 64px;
    height: 64px;
    position: relative;
    left: 0;
    top: 0;
}
.detail-title-wrap .dc-profile{
    font-size: 12px;
    color: #9199a1;
    line-height: 24px;
}
.dc-profile .spacer{
    margin-right: 24px
}
</style>

