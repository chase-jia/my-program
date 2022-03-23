<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			    <!-- 这里是状态栏 -->
			   </view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">购物车</view>
			</view>
		</view>
		<view class="maincontent">
			<view class="__bdi">
				<view class="tj-item" v-for="(item,index) in tjList" :key="item.id"  @click="toDetail(item.id)">
					<image :src="item.src" mode="" class="tu"></image>
					<image :src="item.shoucang" mode="" class="shoucang" @click="shoucang(item)"></image>
					<image :src="item.xuanze" mode="" class="xuanze" @click="xuanze(item)"></image>
					<text class="_s">{{item.title}}</text>
					<text class="_p">￥{{item.price}}</text>
				</view>
			</view>
			<view class="empty">
				
			</view>
		</view>
		<view class="botm">
			<view class="allprice" v-model="allprice">￥{{this.allprice}}</view>
			<view class="submit">提交</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				syy:{
					url:"../../pages/my/my"
				},
				allprice:"0.00",
				tjList:[
					{
						id:"0",
						src:"../../static/shu/shu1.jpg",
						title:"写作60篇",
						price:"36.50",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"1",
						src:"../../static/shu/shu2.jpg",
						title:"京瓷哲学",
						price:"29.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"2",
						src:"../../static/shu/shu3.jpg",
						title:"长尾理论",
						price:"22.70",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"3",
						src:"../../static/shu/shu4.jpg",
						title:"庄子",
						price:"34.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},{
						id:"4",
						src:"../../static/shu/shu6.jpg",
						title:"潜书",
						price:"12.50",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"5",
						src:"../../static/shu/shu1.jpg",
						title:"写作60篇",
						price:"39.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"6",
						src:"../../static/shu/shu2.jpg",
						title:"京瓷哲学",
						price:"29.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					{
						id:"7",
						src:"../../static/shu/shu3.jpg",
						title:"长尾理论",
						price:"22.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},{
						id:"8",
						src:"../../static/shu/shu3.jpg",
						title:"长尾理论",
						price:"22.00",
						shoucang:"../../static/shu/shoucang1.png",
						xuanze:"../../static/shu/xuanze1.png",
						xuancheck:"false",
					},
					
				]
			}
		},
		methods: {
			fanhui(e){
				uni.switchTab({
					url: e.url
				})
			},
			toDetail(id){
				uni.navigateTo({
					//李佳蓉学姐做的
				})
			},
			shoucang(e){
				if(e.shoucang!="../../static/shu/shoucang2.png"){
					e.shoucang = "../../static/shu/shoucang2.png";
					// fanhui(this);//合并之后跳到贾昊鹏写的收藏里
				}else{
					e.shoucang = "../../static/shu/shoucang1.png"
				}
				
			},
			xuanze(e){
				e.xuancheck = !e.xuancheck;
				var allp = parseFloat(this.allprice);
				var shu = parseFloat(e.price);
				if(e.xuancheck==true){
					e.xuanze = "../../static/shu/xuanze1.png";//没选上
					allp = allp - shu;
				}else{//选上了
					e.xuanze = "../../static/shu/xuanze2.png";
					allp = allp + shu;
				}
				this.allprice = Number(allp).toFixed(2);
			}
		}
	}
</script>

<style lang="scss">
	.status_bar {
	  height: var(--status-bar-height);
	  width: 100%;
	  
	 }
	 .tou{
	 	position: fixed;
	 	height: 100upx;
	 	width: 100%;
	 	z-index: 5;
	 	top: 0;
	 	left: 0;
	 	background-color: #50d8be;
	 	box-sizing: border-box;
	.top{
		width: 100%;
		height: 90upx;
		background-color: #50d8be;
		position: relative;
		display: flex;//弹性布局
		align-items: center;
		justify-content: center;
		.jt{
			position: absolute;
			width: 45upx;
			height: 45upx;
			left: 50upx;
			font-size: 45upx;
			
		}
		.zi{
			position: absolute;
			color: #393939;
			font-size: 45upx;
			border-bottom: 6upx #FFFFFF solid;
			font-weight: bold;
		}
	}
	
}
.maincontent{
	width: 100%;
	.__bdi{
		margin-top: 200upx;
		display: flex;
		flex-wrap: wrap;
		
		.tj-item{
			width: 40%;
			padding:10upx;
			margin-left: 50upx;
			margin-bottom: 30upx;
			height: 500upx;
			background:linear-gradient(#ffffff,#aaf7ff,#FFFFFF);
			border: 6upx #42c7e4 solid;
			.tu{
				width: 100%;
				height: 300upx;
			}
			._s{
				display: flex;
				margin: 10upx;
				font-weight: bold;
			}
			._p{
				display: flex;
				color: #bf0303;
				margin: 10upx;
			}
			.shoucang{
				width: 40upx;
				height: 40upx;
				margin-left: 60%;
				margin-top: 10upx;
			}
			.xuanze{
				width: 40upx;
				height: 40upx;
				margin-left: 10upx;
				margin-top: 10upx;
			}
			image{
				width: 40upx;
				height: 40upx;
			}
		}
			
	}
	.empty{
		width: 100%;
		height: 100rpx;
	}
	}

	.botm{
		position: fixed;//相对窗口固定定位
		width: 100%;
		height: 100upx;
		background-color: #50d8be;
		border-radius: 30upx 30upx 0 0;
		bottom: 0;
		display: flex;
		.allprice{
			width: 230upx;
			margin-left: 20upx;
			height: 80upx;
			font-size: 40upx;
			background:linear-gradient(#ffffff,#fffaab,#FFFFFF);
			border: 6upx #d2e42b solid;
			border-radius: 40upx;
			margin-left: 230upx;
			line-height: 70upx;
			text-align: center;
			margin-top: 10upx;
		}
		.submit{
			width: 230upx;
			height: 80upx;
			font-size: 40upx;
			margin-left: 20upx;
			background:linear-gradient(#ffffff,#aaf7ff,#FFFFFF);
			border: 6upx #2B85E4 solid;
			border-radius: 40upx;
			line-height: 70upx;
			text-align: center;
			margin-top: 10upx;
		}
	}
</style>
