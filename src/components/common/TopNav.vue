<template>
    <div class="top-nav">
			<div class="logo">
				<a href="/">十月</a>
			</div>
			<ul>
				<li><a href="/" class="active">首页</a></li>
				<li><a href="/blogs" class="active">文章</a></li>
                <!--<li><a href="/project_demos">作品集</a></li>-->
                <li><a href="/source_sites">资源</a></li>
                <li><a href="/timer">时光轴</a></li>
				<li><a href="/about_us">关于十月</a></li>
			</ul>
    </div>
</template>

<script>

export default{
    name:'name'
}
</script>

<style scoped>
.top-nav{
    height: 60px;
    background:#6987DB;
	margin-left: 0px;
}
.top-nav ul{
    list-style: none;
    margin: 0;
    float: right;
    margin-right: 180px;
}
.top-nav ul li,.top-nav .logo{
    display: inline-block;
    line-height: 60px;
    margin-left: 20px;
}
.top-nav ul li a {
    line-height: 60px;
    text-decoration: none;
    display: inline-block;
    height: inherit;
    color: #fff;
}
.top-nav .logo{
    float: left;
    /* padding: 10px; */
    margin-left: 200px;
}
.logo{
	font-size: 20px;
	font-weight: 700;
	letter-spacing: 2px;/*字体间距*/
}
.logo a{
	color: #fff;
	text-decoration: none;
}
</style>

