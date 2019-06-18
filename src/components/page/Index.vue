//这是主页
<template>
    <div class="main-index">
         <top-nav></top-nav>
         <div class="content">
            <div class="swiper-scoll">
                <swiper :options="swiperOption" ref="mySwiper" class="swiper-list">
                    <!-- slides -->
                    <swiper-slide  class="slide-item" v-for="slide in swiperSlides" :key="slide.index">
                        <a href="http://baidu.com"><img :src="slide" class="scoll-img"></a>
                    </swiper-slide>
                    <!-- Optional controls -->
                    <div class="swiper-pagination"  slot="pagination"></div>
                    <div class="swiper-button-prev" slot="button-prev"></div>
                    <div class="swiper-button-next" slot="button-next"></div>
                </swiper>
             </div>
            <div class="content-bottom">
                <div class="content-left">
                    <div class="left_title">
                        <p>
                            <span>最新新闻</span>
                        </p>
                    </div>

                    <div v-for="article in new_articles" class="article">

                            <div class="article-content">
                                <div>
                                    <a :href = "'blog/'+ article.id + '/detail'" class="article-title" >{{ article.title }}</a>
                                </div>
                                <p class="summary">{{ article.summary }}</p>
                                <div class="meta">
                                    <a class="nick-name" href="">{{ article.user_name }} 发布于 {{ article.created_at}}</a>
                                    <a class="channel" v-if="article.category_name">来自于频道 <strong>{{ article.category_name}}</strong></a>

                                </div>
                            </div>

                    </div>

                </div>
                <div class="content-right">
                    <div class="widget">
                        <h3>
                            热门标签
                        </h3>
                        <div class="special-box">
                                <el-tag class="tag"><a href="#">php</a></el-tag>
                                <el-tag type="success" class="tag">python</el-tag>
                                <el-tag class="tag"><a href="#">Laravel</a></el-tag>
                                <el-tag class="tag" type="danger"><a href="#">vuejs</a></el-tag>
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
import axios from 'axios'
import { Loading } from 'element-ui';

import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default{
    name:'index',
    data(){
        return{
             swiperOption: {
                slidesPerView: 1,
                spaceBetween: 30,
                loop: true,
                pagination: {
                    el: '.swiper-pagination',
                    clickable: true
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                }
            },
            swiperSlides: [
                'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1511015180050&di=0d2ee92eead284e8133d6df07535d75a&imgtype=0&src=http%3A%2F%2Fimg.sc115.com%2Fuploads1%2Fsc%2Fjpgs%2F1512%2Fapic16988_sc115.com.jpg',  
                'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1511015180167&di=7412fd486c47c15f1d27485be0d7bd28&imgtype=0&src=http%3A%2F%2Fwww.duoxinqi.com%2Fimages%2F2012%2F06%2F20120605_8.jpg',  
                'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1511015180050&di=0d2ee92eead284e8133d6df07535d75a&imgtype=0&src=http%3A%2F%2Fimg.sc115.com%2Fuploads1%2Fsc%2Fjpgs%2F1512%2Fapic16988_sc115.com.jpg',
            ],
            new_articles:[]
        }
    },
    components:{
        TopNav,
        FooterNav,
        swiper,
        swiperSlide
    },
    created(){
        //  全屏幕 Loading 服务
        let loadingInstance = Loading.service({fullscreen: true});
        axios.get('http://blog.lovecathy.cn/api/article/new_articles')
            .then(response=>{
                console.log(response);
                this.new_articles = response.data.data
            })
            .catch(error=>{
                console.log(error);
                alert('网络错误，不能访问');
            });
        loadingInstance.close();
    },
}
</script>

<style scoped>
/* @import './../../assets/css/love/default.css'; */
.main-index{
    width: 100%;
    display: flex;
    flex-direction: column;
    /* background-color: #EFF2F7 */
}
.content{
    width: 1000px;
    margin: 0 auto;
    margin-top: 10px;
}
.swiper-scoll{
    width: 100%;
    height: 300px;
}
.scoll-img{
    height: 100%;
    width: 100%;
}
.swiper-list{
    width: 100%;
    height: 300px;
}
.slide-item{
    text-align: center;
}
.content-bottom{
    margin-top: 20px;
    display: flex;
    flex-direction: row;
}
.content-left{
    width: 65%;
    display: flex;
    flex-direction: column;    
}
.left_title{
    float: left;
    width: 100%;
    border-bottom: 1px solid #2333;
}
.left_title p{
    font-size: 15px;
    float: left;
    margin-left: 5px;
}

.article{
    border-bottom: 1px solid #EEE;

    /* width: 80%; */
    /*background-color: #EFF2F7;*/
    height: 120px;
    /*margin-top: 20px;*/
    padding: 10px;
}
.article-content{
    padding: 5px;
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
    height: 40px;
    font-size: 14px;
}
.nick-name{
    text-decoration: none;
    color: #999;
    font-size: 14px;    
}
.content-right{
    margin-left: 10px;
    width: 35%;
    /* border: 1px solid black; */
    padding-top: 50px;
}
.widget{
    border: 1px solid #fdd;
    /* background: #ffff; */
    padding-left: 20px;
    height: 200px;
    /* background: #fdd; */
}
.widget h3{
    border-bottom: 0.0625rem dashed #e6e8eb;
    display: block;
    margin: 0;
    padding: 10px;
}
.special-box{
    padding: 6px;
    display: flex;
    flex-direction: row;
}
.special-box .tag{
    margin: 2px;
}
.special-box a{
    text-decoration: none;
    color: #409EFF;
}
    .channel{
        float: right;
        text-decoration: none;
        color: #999;
        font-size: 14px;
    }
    .channel strong{
        color: black;
    }
</style>

