<template>
    <div class="about-us">
        <el-header> <top-nav></top-nav></el-header>
        <el-main>
            <div class="timer-title">
                <h1>时光轴</h1>
            </div>
            <el-divider></el-divider>
            <el-timeline>
                <el-timeline-item timestamp="2019/6/18" placement="top" type="success">
                    <el-card>
                        <h4>添加时光轴页面</h4>
                        <!--<p>王小虎 提交于 2018/4/2 20:46</p>-->
                    </el-card>
                </el-timeline-item>
                <el-timeline-item timestamp="2019/6/17" placement="top">
                    <el-card>
                        <h4>重构十月的首页</h4>
                        <!--<p>王小虎 提交于 2018/4/3 20:46</p>-->
                    </el-card>
                </el-timeline-item>
                <el-timeline-item>
                </el-timeline-item>
                <el-timeline-item>
                </el-timeline-item>
                <el-timeline-item>

                </el-timeline-item>
            </el-timeline>
        </el-main>

        <el-footer>
            <footer-nav>
            </footer-nav>
        </el-footer>
    </div>
</template>

<script>
import TopNav from '@/components/common/TopNav'
import FooterNav from '@/components/common/FooterNav'
export default {
    name:'about us',
    components:{
       TopNav,
        FooterNav
    }
}
</script>

<style scoped>
    .timer-title h1{
        text-align: center;
    }
    .el-divider{
        max-width: 700px;
        margin: 50px auto;
    }
    .el-header{
        padding:0;
    }
    .el-main{
        margin: 10px 100px;
        min-height: 800px;
        /*background-color: #00a65a;*/
    }
    .el-timeline{
        width: 600px;
        margin:0 auto;
    }
</style>

