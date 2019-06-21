<template>
    <div class="about-us">
        <el-header> <top-nav></top-nav></el-header>
        <el-main>
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>关于我</span>
                </div>
                <div>
                    <p>嘿！你好，我是博客的博主,十月！该博客主要是用来记录我的一些技术点滴， 和一些其他方面的随笔，感悟，生活等。</p>

                    <p>作为一个后端打杂人员，一直想要弄一个自己的博客， 就想自己动手写一个，也算是对自己编码能力的一种试验吧，于是有了这个网站。</p>
                    <p>目前工作于百度，每天都在学习，进步 ~(︿(￣︶￣)︿)</p>
                </div>
            </el-card>
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>联系我</span>
                </div>
                <div>
                    <p>邮箱：625079860@qq.com</p>
                    <p>github: <a href="https://github.com/Jack-Dukang" target="_blank" rel="noopener noreferrer">octorber</a></p>
                </div>
            </el-card>
        </el-main>
        <el-footer>
            <footer-nav></footer-nav>
        </el-footer>
    </div>
</template>

<script>
import TopNav from '@/components/common/TopNav'
import FooterNav from '@/components/common/FooterNav'

export default {
    name:'about us',
    components:{
        TopNav ,
        FooterNav
    }
}
</script>

<style scoped>
    .el-header{
        padding:0;
    }
    .el-main{
        margin: 10px 100px;
        min-height: 800px;
        /*background-color: #00a65a;*/
    }
    .el-card{
        max-width: 760px;
        margin-left: 100px;
        line-height: 20px;
        margin-bottom: 50px;
    }
    .el-card .clearfix{
        text-align: center;
        font-size: 1.5em;
    }
</style>

