<template>
    <div class="sites">
        <top-nav></top-nav>
        <div class="content">
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>前端资源</span>
                </div>
                <div class="item-list">
                    <!--<el-col :span="3"  >-->
                        <el-tooltip placement="top" effect="light" v-for = "(item,index) in frontLists" :key="index">
                            <div slot="content">{{item.content}}</div>
                            <a :href="item.url" class="title"><el-tag type="success">{{item.title}}</el-tag></a>
                        </el-tooltip>
                    <!--</el-col>-->
                </div>
                
            </el-card>

            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>后端资源</span>
                </div>
                <div class="item-list">
                    <el-tooltip placement="top" effect="light" v-for = "(item,index_backend) in backendLists" :key="index_backend">
                        <div slot="content">{{item.content}}</div>
                        <a :href="item.url" class="title"><el-tag type="info">{{item.title}}</el-tag></a>
                    </el-tooltip>
                </div>
            </el-card>

            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>社区资源</span>
                </div>
                <div class="item-list">
                    <el-tooltip placement="top" effect="light" v-for = "(item,index_social) in socialLists" :key="index_social">
                        <div slot="content">{{item.content}}</div>
                        <a :href="item.url" class="title"><el-tag type="danger">{{item.title}}</el-tag></a>
                    </el-tooltip>
                </div>
            </el-card>
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>工具资源</span>
                </div>
                <div class="item-list">
                    <el-tooltip placement="top" effect="light" v-for = "(item,index_tools) in backendLists" :key="index_tools">
                        <div slot="content">{{item.content}}</div>
                        <a :href="item.url" class="title"><el-tag type="warning">{{item.title}}</el-tag></a>
                    </el-tooltip>
                </div>
            </el-card>
        </div>
        <footer-nav></footer-nav>
    </div>
</template>

<script>
    import TopNav from '@/components/common/TopNav'
    import FooterNav from '@/components/common/FooterNav'
    export default{
        name:'source_sites',
        data(){
                return{
                    'frontLists' : [
                        {
                            'content' : 'Vue.js官网',
                            'url' : 'https://cn.vuejs.org/',
                            'title' : 'Vue.js官网',
                        },
                        {
                            'content' : 'Vue技术内幕，逐行级别的 Vue 源码分析',
                            'url' : 'http://hcysun.me/vue-design/',
                            'title' : 'Vue.js源码分析',
                        },
                        {
                            'content' : 'Element UI',
                            'url' : 'http://element-cn.eleme.io/#/zh-CN',
                            'title' : 'Element UI',
                        },
                        {
                            'content' : '技术胖 前端免费技术学习视频',
                            'url' : 'http://jspang.com',
                            'title' : '技术胖免费前端学习',
                        }
                    ],
                    'backendLists' :[
                        {
                            'content' : 'PHP官网',
                            'url' : 'http://www.php.net/',
                            'title' : 'PHP官网',
                        },
                        {
                            'content' : 'LaravelChina社区',
                            'url' : 'https://laravel-china.org/',
                            'title' : 'LaravelChina社区',
                        },
                        {
                            'content' : 'Laravel-admin是一个可以快速帮你构建后台管理的工具',
                            'url' : 'http://laravel-admin.org/docs/#/zh/',
                            'title' : 'Laravel-admin',
                        },
                        {
                            'content' : 'Laravel学院',
                            'url' : 'http://laravelacademy.org/',
                            'title' : 'Laravel学院',
                        },
                    ],
                    'socialLists':[
                        {
                            'content' : 'Love2.io 是一个全新的开源技术文档分享平台，很多优秀的技术文档',
                            'url' : 'https://github.com/thx/rap2-delos',
                            'title' : 'Love2.io',
                        },
                        {
                            'content' : '阿里妈妈前端团队出品的开源接口管理工具RAP第二代',
                            'url' : 'https://github.com/thx/rap2-delos',
                            'title' : 'RAP接口管理工具',
                        },
                        {
                            'content' : '开发手册',
                            'url' : 'https://docs.segmentfault.com/',
                            'title' : '技术开发手册',
                        },
                        {
                            'content' : '掘金',
                            'url' : 'https://juejin.im/',
                            'title' : '掘金',
                        }
                    ],
                    'toolLists':[
                        {
                            'content' : '爱情守望者',
                            'url' : 'https://www.waitsun.com/',
                            'title' : '爱情守望者',
                        },
                        {
                            'content' : '漂亮的代码截图',
                            'url' : 'https://carbon.now.sh/',
                            'title' : '漂亮的代码截图',
                        }
                    ],
                    'loading' :true
                }
        },
        components:{
            TopNav,
            FooterNav
        }
    }
</script>

<style scoped>

    .content{
        width: 1000px;
        display: flex;
        flex-direction: column;
        margin: 10px auto;
    }
    .clearfix{
        text-align: left;
    }
    .clearfix:before,
    .clearfix:after {
        display: table;
        content: "";
    }
    .clearfix:after {
        clear: both
    }
    .box-card {
        width: 1000px;
        margin-bottom: 20px;
        height: 100%;
    }
    .box-card .item-list{
        padding: 2px;
        min-height: 120px;
        line-height: 20px;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
    }
    .box-card .item-list a{
        margin-left: 10px;
        margin-bottom: 15px;
        text-align: center;
        font-size: 25px;
    }
</style>


