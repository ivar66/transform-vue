<template>
    <div class="content">
        <top-nav></top-nav>
        <div class="article-content1">
            <div class="article-filter">
                <el-radio-group>
                    <el-radio-button :label="false">最热</el-radio-button>
                    <el-radio-button :label="true">最新</el-radio-button>
                </el-radio-group>
                <!-- <el-dropdown>
                    <span class="el-dropdown-link">
                        下拉菜单<i class="el-icon-arrow-down el-icon--right"></i>
                    </span>
                    <el-dropdown-menu slot="dropdown">
                        <el-dropdown-item>社区</el-dropdown-item>
                        <el-dropdown-item divided>论坛</el-dropdown-item>
                    </el-dropdown-menu>
                </el-dropdown> -->
            </div>
            <div class="article-list">
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
                    <div class="article">
                        <div class="img-wrap" style="display:none">
                            <img class="img-blur-done" src="//upload-images.jianshu.io/upload_images/147412-4e850cf87577b71a.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240" alt="">
                        </div>
                        <div class="article-content">
                            <a class="article-title" href="#" >微信发展简史：微信成功的必然和偶然</a>
                            <p class="summary">微信是互联网圈永远的热点，这不，这两天突然微信又成了话题中心，原因有两个： 1、微信更新版本，做了一个『浮窗』，有了这个小小的浮窗，用户可以在聊...</p>
                            <div class="meta">
                                <a class="nick-name" href="#">行者慎思</a>
                            </div>
                        </div>
                    </div>
            </div>
        </div>
        <footer-nav></footer-nav>
    </div>
</template>

<script>
import TopNav from '@/components/common/TopNav'
import FooterNav from '@/components/common/FooterNav'

export default {
    name:'article',
    components:{
        TopNav,
        FooterNav
    },
    created(){
        console.log(this.$route.query);
    }
}
</script>

<style scoped>
.content{
    display: flex;
    flex-direction: column;
    background: rgb(240, 242, 245);
}

.article-content1{
    width: 1000px;
    margin: 20px auto;
    display: inline-flex;
    flex-direction: column;
}
.article-filter{
    padding: 20px 32px;
    display: flex;
    justify-content:space-between;
    background: #FAFBFC;
    box-shadow: inset 0 -1px 0 0 #DDE2F0;
}
.article-list{
    background: #FAFBFC;
    display: flex;
    flex-direction: column;
}
.article{
    height: 140px;
    padding: 5px;
    box-shadow: inset 0 -1px 0 0 #DDE2F0;
}
.article .article-content{
    padding: 15px;
    text-align: left;
}
.article-title{
    font-size: 18px;
    text-decoration: none;
    display: inherit;
    color: rgb(35, 48, 63);
}
.summary{
    margin-top: 10px;
    color: #999;
    font-size: 14px;
}
.nick-name{
    text-decoration: none;
    color: #999;
    font-size: 14px;    
}

</style>

