<template>
	<div>
		<div class="xmh-menu-bgc"></div>
		
		<div class="xmh-header">
			<div class="xmh-quick-menu">
				<div class="xmh-qheader">
					<ul class="xmh-mos"> 
					<li class="xmh-mos-a">
							<span class="xmh-link-none">小米商城</span>
						</li>
						<li class="xmh-mos-a">
							<span class="xmh-link-none">MIUI</span>
						</li>
						<li class="xmh-mos-a">
							<span class="xmh-link-none">IOT</span>
						</li>
						<li class="xmh-mos-a">
							<span class="xmh-link-none">云服务</span>
						</li>
						<li class="xmh-mos-a">
							<span class="xmh-link-none">金融</span>
						</li>
						<li class="xmh-mos-a">
						<span class="xmh-link-none">小爱开放平台</span>
						</li>
						<li class="xmh-mos-a">
					      <a href="https://www.mi.com/appdownload"><span class="xmh-link-app">下载app</span></a>
						</li>
						<li class="xmh-mos-a">
							<span class="xmh-link-none">SelectRegion</span>
						</li>
					</ul>
				</div>
				
				
				<ul class="xmh-mos-item">
					<li class="xmh-item">
						 <a href="http://127.0.0.1:8848/web01/xiaomihome/src/log.html"><span class="xmh-link-app">登录</span></a>
					</li>
					<li class="xmh-item">
						<router-link class="xmh-link" to="/order">我的订单</router-link>
					</li>
					<li class="xmh-item">
					<router-link class="xmh-link" to="/cart">&nbsp;购物车</router-link>
					</li>
					<li class="xmh-item">
						<span class="xmh-link-Y">消息通知</span>
					</li>
					<li class="xmh-item">
					     <span class="xmh-link-Y">精选</span>
					</li>
				</ul>
			</div>
			<div >
				<div class="xmh-logo" @click="toHomepage"></div>
			
						
				<div class="xmh-search-box">
					<input class="xmh-search-input" type="text" placeholder="小米9 小米9s">
					<span class="xmh-search-btn">搜&nbsp;&nbsp;索</span>
				</div>
			</div>
		</div>
		<div class="xmh-dividor"></div>
		<router-view />
	</div>
</template>

<script>

	export default {
		name: 'App',
		methods: {
			toHomepage() {
				this.$router.push('/')
			}
		}
	}
</script>

<style>
	
	.xmh-link-app{
		color: #999;
		text-decoration: none;
		outline: none;
	}
	.xmh-link {
		color: #999;
		text-decoration: none;
		outline: none;
	}
	
	.xmh-menu-bgc{
		position: absolute;
		width: 100%;
		height: 50px;
		background-color: #000000;
		border-bottom: 1px solid #ffaa7f;
	}
	.xmh-header{
		width:1120px;
		margin-left: auto;
		margin-right: auto;
	}
	.xmh-quick-menu{
		position: relative;
		font-size: 12px;
		color: #ffffff;
		background-color: #000000;
	}
	.xmh-qheader{
		display: inline-block;
		line-height: 50px;
		cursor: pointer;
	}
	.xmh-mos{
		position: absolute;
		left: 0;
		display: inline-block;
		line-height: 1px;
		list-style: none;
	}
	.xmh-mos-a{
		margin-left: 12px;
		display: inline-block;
	}
	.xmh-link-none{
		color: #999;
		text-decoration: none;
		outline: none;
	   
	}
	.xmh-mos-item{
		position: absolute;
		right: 0;
		display: inline-block;
		line-height: 25px;
		list-style: none;
	}
	.xmh-item{
		margin-left: 12px;
		display: inline-block;
	}
	.xmh-link-Y{
		color: #999;
		text-decoration: none;
		outline: none;
		cursor: not-allowed;
	}
	.xmh-logo{
		display: inline-block;
		margin-top: 50px;
		margin-bottom: 20px;
		width: 188px;
		height: 70px;
		cursor: pointer;
		background-image: url(./assets/images/logo.jpg);
		background-repeat: no-repeat;
		background-size: 90px 90px;
	}
	

	
	.xmh-search-box {
		display: inline-block;
		line-height: 170px;
		float: right;
	}
	
	.xmh-search-input {
		box-sizing: border-box;
		width: 240px;
		line-height: 32px;
		padding-left: 6px;
		outline: none;
		border: 2px solid #e5711d;
		vertical-align: middle;
	}
	
	.xmh-search-btn {
		display: inline-block;
		line-height: 35px;
		padding-left: 16px;
		padding-right: 15px;
		color: #fff;
		font-weight: 600;
		background-color: #e5711d;
		vertical-align: middle;
		cursor: pointer;
		user-select: none;
	}
	
	
	.xmh-dividor {
		height: 2px;
		background-color: #e5711d;
	}
</style>