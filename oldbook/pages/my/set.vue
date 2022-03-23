<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">设置</view>
			</view>
		</view>
		<view class="xxk">
			<view class="xk"
			v-for="(item,index) in chooseList"
			:key="index">
				<view class="text">{{item.name}}</view>
				<image src="../../static/shu/yj.png" mode="" @click="tiaozhuan(item)"></image>
			</view>
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
				chooseList:[{
					name:"账号绑定",
					url:"../../pages/my/zhbd"
				},{
					name:"实名认证",
					url:"../../pages/my/smrz"
				},{
					name:"帮助与反馈",
					url:"../../pages/my/help"
				},{
					name:"清除缓存",
					url:"../../pages/my/clear"
				},{
					name:"隐私政策",
					url:"../../pages/my/private"
				},{
					name:"用户协议",
					url:"../../pages/my/yhxy"
				}]
			}
		},
		methods: {
			tiaozhuan(e) {
				uni.navigateTo({
					url: e.url
				});
			},
			fanhui(e){
				uni.switchTab({
					url: e.url
				})
			},
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
			/* #ifdef MP-WEIXIN */
					//解决微信小程序的胶囊问题
					width: calc(100% - 95px);
					/* #endif */
					/* #ifndef MP-WEIXIN*/
					width: 100%;
					/* #endif*/

			width: 100%;
			height: 100upx;
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
	.xxk{
		button::after{
			border: none;
		}
		margin-top: 200upx;
		display: flex;
		height: 900upx;
		box-sizing: border-box;
		text-align: center;
		flex-direction: column;//垂直方向自上而下的排列方式
		align-items: center;
		.xk{
			display: flex;
			box-sizing: border-box;
			height: 100upx;
			width: 100%;
			justify-content: space-between;
			margin-top: 40upx;
			border-top: 6upx #f4f4f4 dashed;
			border-bottom: 6upx #f4f4f4 dashed;
			background-color: #ececec;
			image{
				margin-top: 25upx;
				width: 40upx;
				height: 40upx;
				margin-right: 50upx;
			}
			.text{
				margin-top: 8upx;
				margin-left: 50upx;
				height: 70upx;
				font-size: 40upx;
				color: #50d8be;
				line-height: 70upx;
				text-align: center;
			}
		}
		
	}
</style>
