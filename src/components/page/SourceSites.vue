<template>
    <div class="sites">
        <top-nav></top-nav>
        <div class="content">
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>前端资源</span>
                </div>
                <div class="item-list">
                    <el-col :span="3" v-for = "(item , i) in felists" >
                        <el-tooltip placement="top" effect="light">
                            <div slot="content">{{item.content}}</div>
                            <a :href="item.url" class="title">{{item.title}}</a>
                        </el-tooltip>
                    </el-col>
                </div>
                
            </el-card>

            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>后端资源</span>
                </div>
                <div class="item-list">
                    <el-col :span="3">
                        <el-tooltip content="PHP官网" placement="top" effect="light">
                             <a href="http://www.php.net/" class="title">PHP官网</a>
                        </el-tooltip>
                    </el-col>
                    <el-col :span="3">
                        <el-tooltip content="LaravelChina社区" placement="top" effect="light">
                             <a href="https://laravel-china.org/" class="title">LaravelChina社区</a>
                        </el-tooltip>
                    </el-col>
                    <el-col :span="3">
                        <el-tooltip content="Laravel学院" placement="top" effect="light">
                             <a href="http://laravelacademy.org/" class="title">Laravel学院</a>
                        </el-tooltip>
                    </el-col>      
                    <el-col :span="3">
                        <el-tooltip content="laravel-admin是一个可以快速帮你构建后台管理的工具" placement="top" effect="light">
                             <a href="http://laravel-admin.org/docs/#/zh/" class="title">laravel-admin</a>
                        </el-tooltip>
                    </el-col>   
                             
                </div>
            </el-card>
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>社区资源</span>
                </div>
                <div class="item-list">
                    
                    <el-col :span="3">
                         <el-tooltip content="SegmentFault" placement="top" effect="light">
                             <a href="https://segmentfault.com/" class="title">SegmentFault</a>
                        </el-tooltip>
                    </el-col>
                    <el-col :span="3">
                        <el-tooltip content="掘金" placement="top" effect="light">
                             <a href="https://juejin.im/" class="title">掘金</a>
                        </el-tooltip>
                    </el-col>         
                    <el-col :span="3">
                        <el-tooltip content="开发手册" placement="top" effect="light">
                             <a href="https://docs.segmentfault.com/" class="title">技术开发手册</a>
                        </el-tooltip>
                    </el-col>                    
                    <el-col :span="3">
                        <el-tooltip content="阿里妈妈前端团队出品的开源接口管理工具RAP第二代" placement="top" effect="light">
                             <a href="https://github.com/thx/rap2-delos" class="title">RAP接口管理工具</a>
                        </el-tooltip>
                    </el-col>
                    <el-col :span="3">
                        <el-tooltip content="Love2.io 是一个全新的开源技术文档分享平台，很多优秀的技术文档" placement="top" effect="light">
                             <a href="https://github.com/thx/rap2-delos" class="title">Love2.io</a>
                        </el-tooltip>
                    </el-col>
                </div>
            </el-card>
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>工具资源</span>
                </div>
                <div class="item-list">
                    <el-col :span="3">
                        <el-tooltip content="爱情守望者" placement="top" effect="light">
                             <a href="https://www.waitsun.com/" class="title">爱情守望者</a>
                        </el-tooltip>
                    </el-col>
                    <el-col :span="3">
                        <el-tooltip content="漂亮的代码截图" placement="top" effect="light">
                             <a href="https://carbon.now.sh/" class="title">Carbon代码截图</a>
                        </el-tooltip>
                    </el-col>                      
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
                    'felists' : [
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
        margin: 20px auto;
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
        text-align: left;
        margin-top: 20px;
        height: 100%;
    }
    .box-card .item-list{
        padding: 2px;
        height: 140px;
        line-height: 30px;
          /* display: flex; */
          /* flex-direction: row; */
    }
    .box-card{
        float: left;
    }
    .box-card a{
        text-decoration: none;
        color: #999b9d;
        margin: 4px auto;
        width: 100px;
        text-align: left;
        white-space:nowrap;
        overflow:hidden;
        text-overflow: ellipsis;
        display: block;
        font-size: 16px;
        border: 0.0625rem dashed #e6e8eb;
    }

</style>


