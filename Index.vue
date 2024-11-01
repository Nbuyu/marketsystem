<template>
	<div class="container">
		<div class="swiper-bg" :style="{backgroundColor: slidesColor[index]}"></div>
		<div class="stage">
			<ul class="xmh-nav">
				<li v-for="(item, index) in navbars" :key="index" class="cate-nav-item">
					{{ item.text }}
				</li>
			</ul>
			<div class="swiper">
			
				<Swiper :slides="slidesImage" v-model="index"></Swiper>
			</div>
		</div>
		
		<div class="xm-ba">
			<h2 class="spjs">商品介绍</h2>
			<ul class="xm-list">
				<li class="xm-re" v-for="(item,index) in goods":key="index" @click="togglePage(item)" >
					<img class="xm-me" :src="getImg(item.cover)"/>
					<div class="xm-pr">
						<h4>{{item.text}}</h4>
						<p class="xm-pa">
							原价: <span class="xm-price">￥{{ item.price }}</span>&nbsp;
							促销价: <span class="xm-online-price">￥{{ item.onlinePrice }}</span>
						</p>
					</div>
				</li>
			
			</ul>
		</div>
	</div>
	
</template>


<script>
	import Swiper from '@/widgets/Swiper'
	import config from '@/config/config'
	export default{
		name: 'Index',
		components: {
			Swiper
		},
		data() {
			return {
				index: 0
			}
		},
		computed: {
			navbars() {
				return config.navbars
			},
			goods() {
				return config.goods
			},
			slidesColor() {
				return config.goods.map(item => item.color)
			},
			slidesImage() {
				return config.goods.map(item => item.poster)
			}
		},
		methods: {
			togglePage(item) {
				this.$router.push({
					path: '/goods',
					query: {
						name: item.name
					}
				})
			},
			getImg(img) {
				return require(`@/assets/${img}`)
			}
		}
	}
	
</script>

<style scoped>
	
	.container {
		position: relative;
		background-color: #f5f5f5;
		border-bottom: 1px solid transparent;
	}
	
	.swiper-bg {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 500px;
		background-color: #e5e5e5;
	}
	.stage {
		width: 1120px;
		margin-left: auto;
		margin-right: auto;
		background-color: #789;
	}
	
	.xmh-nav {
		display: inline-block;
		position: absolute;
		width: 200px;
		height: 500px;
		margin-top: 0px;
		z-index: 2;
	
		list-style: none;
		background-color: rgba(0, 0, 0, 0.55);
	}
	.cate-nav-item {
		padding-left: 12px;
		line-height: 35.7143px;
		color: #fff;
		cursor: pointer;
	}
	
	.cate-nav-item:hover {
		color: #787878;
		background-color: rgba(255, 255, 255, .8);
	}
	.cate-nav-icon {
		opacity: .5;
	}
	
	.swiper {
		height: 500px;
		background-color: #e8e8e8;
	}
	
	.xm-ba {
		margin: 30px auto;
		padding-top: 30px;
		padding-bottom: 50px;
		width: 1120px;
		background-color:#fff;
	}
	
	.spjs{
		padding: 8px 15px;
	}
	
	.xm-list {
		list-style: none;
	}
	
	.xm-re {
		display: inline-block;
		width: 25%;
		text-align: center;
		vertical-align: top;
		cursor: pointer;
	}
	
	.xm-me {
		width: 240px;
	}
	
	.xm-pr{
		width: 200px;
		display: inline-block;
		color: #444;
	}
	
	.xm-price {
		text-decoration: line-through;
	}
	
	.xm-online-price {
		color: #ff0036;
		font-size: 16px;
	}
	
	.xm-pa{
		font-size: 12px;
		color: #888;
	}
</style>