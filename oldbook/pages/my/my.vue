<template>
	<view>
		<!-- <view class="tou">
			<view class="status_bar">
			   </view>
			<view class="top">
			</view>
		</view> -->

		<view class="navigate">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<text>我的页面</text>
			</view>
		</view>

		<image src="../../static/shu/backimg-1.jpg" mode="" class="backimg"></image>

		<!-- <view class="" v-if="islogin">
			
		</view>
		<view class="" v-else="">
			
		</view> -->
		
		
		
		<view class="di" v-if="islogin">
			<view class="zj">
				<button type="default" class="shezhi" v-model="set" @click="tiaozhuan(set)">设置</button>
				<image src="../../static/shu/touxiang.jpg" mode="" class="touxiang" @click="show"></image>
				<button type="default" class="bianji" v-model="write" @click="tiaozhuan(write)">编辑</button>
			</view>
			<view class="grxx">
				<view class="name" v-model="people">{{people.name}}</view>
				<view class="sex" v-model="people">{{people.sex}}</view>
				<view class="dengji" v-model="people">{{people.dengji}}</view>
				<view class="idid" v-model="people">{{people.idid}}</view>
				<view class="yhid" v-model="people">{{people.yhid}}</view>
			</view>
			<view class="shop" v-model="dian" @click="tiaozhuan(dian)">
				<image src="../../static/shu/shopping.png" mode=""></image>
				<view class="car">购物车</view>
			</view>
			<view class="friends" v-model="friends" @click="tiaozhuan(friends)">
				<image src="../../static/shu/friends.png" mode=""></image>
				<view class="boy">好友列表</view>
			</view>

		</view>
		
		<view class="no-login" v-else="">
			<view class="smallflex">
				<image src="../../static/lovely-dog.png" mode=""></image>
				<text>你还没有登录哦</text>
			</view>
			<button type="default" @click="tologin">点击登录</button>
		<!-- 	<button type="default" @click="clear"></button> -->
		</view>
		
		<view class="changeover" v-show="isshow">
			<text>是否确认退出登录</text>
			<view class="smallchange">
				<button type="default" @click="toone">确认</button>
				<button type="default" @click="totwo">取消</button>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				people: {
					name: "可爱的巴扎黑",
					touxiang: "../../static/shu/1.png",
					sex: "女",
					birthday: "2001-6-22",
					dengji: "Lv6",
					idid: "用户id",
					yhid: "610726",
					
				},
				islogin:false,
				isshow:false,
				change:false,
				set: {
					ulL: "../../pages/my/set"
				},
				write: {
					ulL: "../../pages/my/write"
				},
				dian: {
					ulL: "../../pages/my/gwc"
				},
				friends: {
					ulL: "../../pages/my/friends"
				}
			}
			},
		onShow(){
			this.islogin=getApp().globalData.$islogin;
			if(this.islogin){
				this.change=true;
			}else{
				this.change=false;
			}
			// getApp().globalData.$islogin=false;
		},
		onLoad() {
			if(!this.change){
				uni.navigateTo({
					url:"./login"
				})
			}
			
		},
		created() {
			this.islogin=getApp().globalData.$islogin;
		}
		,
		methods: {
			tiaozhuan(e) {
				uni.navigateTo({
					url: e.ulL
				})
			},
			tologin(){
				uni.navigateTo({
					url:"./login"
				})
			},
			clear(){
				uni.clearStorage();
			},
			toone(){
				this.isshow=false;
				getApp().globalData.$islogin=false;
				uni.navigateTo({
					url:"./login"
				})
			},
			totwo(){
				this.change=true;
				this.isshow=false;
				
				
			},
			show(){
				this.isshow=true;
			}
		}
	}
</script>

<style lang="scss">
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}
.navigate {
		/* #ifdef MP-WEIXIN */
		//解决微信小程序的胶囊问题
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN*/
		width: 100%;

		/* #endif*/
		
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 100;
		background: rgba(255, 255, 255, 1);
		box-sizing: border-box;
		background-color: #50d8be;
		left: 0;
		.head {

			height: 80rpx;
			background-color: #50d8be;
			display: flex;
			justify-content: space-around;
			align-items: center;

			text {
				// margin: 18rpx 0 0 240rpx;
				font-size: 35rpx;
				font-weight: bold;
				color: white;
			}
		}
	}
	
	.changeover{
		position: fixed;
		top: 500rpx;
		left: 0;
		width: 80%;
		height: 200rpx;
		margin-left: 10%;
		background-color: #8a8a8a;
		z-index: 100;
		text-align: center;
		text {
			font-size: 35rpx;
			font-weight: bold;
			color: #50d8be;
			
		}
		.smallchange{
			height: 160rpx;
			width: 100%;
			display: flex;
			justify-content: space-around;
			align-items: center;
			button{
				margin-top: 50rpx;
				width: 250rpx;
				height: 100rpx;
				border: 2rpx  #50d8be solid;
			}
			
		}
	}
	.no-login {
		width: 100%;
		height: 500rpx;
		margin-top: 50rpx;

		.smallflex {
			margin: 0 auto;
			width: 50%;
			height: 100rpx;
			display: flex;
			justify-content: space-around;
			align-items: center;

			image {
				height: 100rpx;
				width: 100rpx;
			}

			text {
				font-size: 35rpx;
				font-weight: bold;
				color: #50d8be;
			}
		}
		button{
			margin-top: 50rpx;
			width: 300rpx;
			height: 100rpx;
			border: 2rpx  #50d8be solid;
		}

	}

	

	// .status_bar {
	//   height: var(--status-bar-height);
	//   width: 100%;
	//  }
	//  .tou{
	//  	position: fixed;
	//  	height: 100upx;
	//  	width: 100%;
	//  	z-index: 5;
	//  	top: 0;
	//  	left: 0;
	//  	background-color: #50d8be;
	//  	box-sizing: border-box;
	// 	.top{
	// 		/* #ifdef MP-WEIXIN */
	// 		//解决微信小程序的胶囊问题
	// 		width: calc(100% - 95px);
	// 		/* #endif */
	// 		/* #ifndef MP-WEIXIN*/
	// 		width: 100%;
	// 		/* #endif*/
	// 		// position: relative;
	// 		width: 100%;
	// 		height: 560upx;
	// 		display: flex;
	// 	}
	// }
	.backimg {
		width: 100%;
		height: 570upx;
		// position: absolute;
		z-index: 1;
	}

	.di {
		position: relative;

		.zj {
			display: flex;
			margin-bottom: 20upx;

			.shezhi {
				width: 180upx;
				height: 50upx;
				line-height: 50upx;
				position: absolute;
				border: 2upx solid #50d8be;
				border-radius: 25upx;
				z-index: 6;
				right: 50upx;
				margin-top: -120upx;
			}

			.touxiang {
				width: 130upx;
				height: 130upx;
				border-radius: 50%;
				border: 4upx solid #50d8be;
				z-index: 3;
				// position: absolute;
				margin-top: -75upx;
				margin-left: 50upx;
			}

			.bianji {
				width: 150upx;
				height: 60upx;
				// position: absolute;
				margin-top: 20upx;
				margin-left: 70upx;
				font-size: 30upx;
				line-height: 50upx;
				border-radius: 25upx;
				border: 2upx solid #50d8be;
				z-index: 3;
			}
		}

		.grxx {
			height: 140upx;
			position: relative;

			.name {
				position: absolute;
				color: #383838;
				font-weight: 900;
				top: 10upx;
				left: 50upx;
				font-size: 30upx;
			}

			.sex {
				position: absolute;
				width: 66upx;
				height: 40upx;
				line-height: 40upx;
				background-color: #e28ec7;
				border-radius: 20upx;
				left: 300upx;
				text-align: center;
				top: 6upx;
				font-weight: bold;
			}

			.dengji {
				position: absolute;
				width: 66upx;
				height: 40upx;
				line-height: 40upx;
				background-color: #ece34e;
				border-radius: 20upx;
				left: 630upx;
				text-align: center;
				top: 6upx;
				font-weight: bold;
			}

			.idid {
				position: absolute;
				width: 130upx;
				height: 40upx;
				color: #a6aec5;
				top: 70upx;
				left: 50upx;
				font-size: 30upx;
			}

			.yhid {
				position: absolute;
				color: #383838;
				font-weight: 900;
				top: 70upx;
				left: 170upx;
				font-size: 30upx;
			}
		}

		.shop {
			width: 680upx;
			height: 250upx;
			position: relative;
			display: flex;
			background-color: #edf1f2;
			margin: 15upx auto;
			border-radius: 20upx;

			image {
				width: 375upx;
				height: 240upx;
				align-items: center;
				left: 300upx;
				position: absolute;
				top: 8upx;
			}

			.car {
				position: relative;
				left: 70upx;
				top: 45upx;
				font-size: 45upx;
				color: #50d8be;
			}
		}

		.friends {
			width: 680upx;
			height: 250upx;
			position: relative;
			display: flex;
			background-color: #edf1f2;
			margin: 15upx auto;
			border-radius: 20upx;

			image {
				width: 375upx;
				height: 240upx;
				align-items: center;
				left: 300upx;
				position: absolute;
				top: 8upx;
			}

			.boy {
				position: relative;
				left: 70upx;
				top: 45upx;
				font-size: 45upx;
				color: #50d8be;
			}
		}

	}
</style>
