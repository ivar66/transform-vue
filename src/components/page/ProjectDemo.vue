<template>
    <div class="project-main">
        <TopNav></TopNav>
        <div class="project-tab">
            <el-tabs type="card" v-model="activeName">
                <el-tab-pane label="前端" name="fe">
                    <el-row class="card-lists">
                            <el-card :body-style="{ padding: '2px' }" class="card-tab" shadow="hover">
                                <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" class="image">
                                <div class="card-tab-content">
                                    <span class="title">好吃的汉堡</span>
                                    <div class="bottom clearfix">
                                    <time class="time">{{ currentDate }}</time>
                                    <el-button type="text" class="button">操作按钮</el-button>
                                    </div>
                                </div>
                            </el-card>
                            <el-card :body-style="{ padding: '2px' }" class="card-tab" shadow="hover">
                                <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" class="image">
                                <div class="card-tab-content">
                                    <span class="title">好吃的汉堡</span>
                                    <div class="bottom clearfix">
                                    <time class="time">{{ currentDate }}</time>
                                    <el-button type="text" class="button">操作按钮</el-button>
                                    </div>
                                </div>
                            </el-card>
                            <el-card :body-style="{ padding: '2px' }" class="card-tab" shadow="hover">
                                <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" class="image">
                                <div class="card-tab-content">
                                    <span class="title">好吃的汉堡</span>
                                    <div class="bottom clearfix">
                                    <time class="time">{{ currentDate }}</time>
                                    <el-button type="text" class="button">操作按钮</el-button>
                                    </div>
                                </div>
                            </el-card>
                            <el-card :body-style="{ padding: '2px' }" class="card-tab" shadow="hover">
                                <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" class="image">
                                <div class="card-tab-content">
                                    <span class="title">好吃的汉堡</span>
                                    <div class="bottom clearfix">
                                    <time class="time">{{ currentDate }}</time>
                                    <el-button type="text" class="button">操作按钮</el-button>
                                    </div>
                                </div>
                            </el-card>
                    </el-row>
                </el-tab-pane>
                <el-tab-pane label="后端" name="be">
                    <el-row class="card-lists">
                            <el-card :body-style="{ padding: '2px' }" class="card-tab" shadow="hover">
                                <img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg" class="image">
                                <div class="card-tab-content">
                                    <span class="title">后端</span>
                                    <div class="bottom clearfix">
                                    <time class="time">{{ currentDate }}</time>
                                    <el-button type="text" class="button">操作按钮</el-button>
                                    </div>
                                </div>
                            </el-card>
                    </el-row>
                </el-tab-pane>
            </el-tabs>
        </div>
        <footer-nav></footer-nav>
    </div>
</template>

<script>
import TopNav from '@/components/common/TopNav'
import FooterNav from '@/components/common/FooterNav'

export default {
    name:'project-demo',
    data(){
        return {
            currentDate: new Date().getTime(),
            activeName:'fe'
        };
    },
    components:{
        TopNav,
        FooterNav
    }
}
</script>

<style scoped>
    .project-tab{
        width: 1100px;
        margin: 0 auto;
        margin-top: 20px;
    }
    /**card**/
    .time {
        font-size: 13px;
        color: #999;
      }

    .bottom {
        margin-top: 13px;
        line-height: 12px;
    }

    .button {
        padding: 0;
        float: right;
    }

    .image {
        width: 100%;
        height: 200px;
        display: block;
    }

    .clearfix:before,
    .clearfix:after {
        display: table;
        content: "";
    }

    .clearfix:after {
        clear: both
    }

    .card-tab{
        width: 300px;
        height: 300px;
        margin: 20px;
    }
    .card-lists{
        display: flex;
        flex-direction: row;
        flex-wrap:wrap;
    }
    .card-tab-content{
        padding: 10px 10px;
        display: flex;
        flex-direction: column;
        text-align: left;
    }

</style>


