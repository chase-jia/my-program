<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">个人信息</text>
			</view>
		</view>
		<view class="top">
			<image src="../../static/shudan/4.jpg" mode=""></image>
			<view class="top1">
				<text class="top11">老笔斋的老猫</text>
				<text class="top12">刚刚来过</text>
				<text class="top13">愿得一人心，白首不分离</text>
			</view>
			<view class="top2">
				<image src="../../static/xiangqing/4.png" mode=""></image>
				<view class="top21">
					<text>学生认证</text>
				</view>
			</view>
		</view>
		<view class="middle">
			<text class="md1">TA的交易</text>
			<view class="md2">
				<view class="md21">
					<text class="md211">1</text>
					<text>在售商品</text>
				</view>
				<view class="md22">
					<text class="md221">1</text>
					<text>已售商品</text>
				</view>
			</view>
		</view>
		<view class="pingjia">
			<view class="pj1">
				<text>TA的评价</text>
			</view>
			<view class="pj2">
				<view class="pj21">
					<text>好评率</text>
					<text>发货时间</text>
					<text>商品互动率</text>
				</view>
				<view class="pj22">
					<text>100%</text>
					<text>1天</text>
					<text>67%</text>
				</view>
			</view>
		</view>
		<view class="liaotian">
			<text>聊一聊</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
		toBack(){
			uni.navigateTo({
				url:"./sesouxq"
			});
		},	
		}
	}
</script>

<style lang="scss">
.status_bar {
		height: var(--status-bar-height);
		width: 100%;
}
.head_bg{
	z-index: 100;
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	background-color: #50d8be;
	border-radius: 0 0 100rpx 100rpx;
	.head{
		height: 100rpx;
		/* #ifdef MP-WEIXIN */
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN */
		width: 100%;
		/* #endif */
		image{
			height: 38rpx;
			width: 38rpx;
			margin-left: 50rpx;
			margin-top: 31rpx;
		}
		.head_txt{
			font-size: 45rpx;
			font-weight: bold;
			color: white;
			margin-left: 215rpx;
		}
	}
}
.top{
	position: relative;
	width: 700rpx;
	height: 200rpx;
	background-color: #ffffff;
	margin:250rpx 25rpx 0 25rpx;
	border-radius: 30rpx;
	display: flex;
	box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
	image{
		width: 160rpx;
		height: 160rpx;
		border-radius: 80rpx;
		margin-left: 35rpx;
		margin-top: 10rpx;
	}
	.top1{
		height: 100rpx;
		margin-left: 30rpx;
		padding-top: 20rpx;
		display: flex;
		flex-direction: column;
		.top11{
			height: 30rpx;
			font-size: 30rpx;
		}
		.top12{
			margin-top: 20rpx;
			font-size: 25rpx;
			color: #808080;
		}
		.top13{
			margin-top: 40rpx;
			font-size: 27rpx;
		}
	}
	.top2{
		width: 180rpx;
		height: 60rpx;
		display: flex;
		position: absolute;
		right: 0;
		top: 0;
		image{
			width: 40rpx;
			height: 40rpx;
			margin-left: 0;
			
		}
		.top21{
			height: 60rpx;
			font-size: 25rpx;
			margin-left: 10rpx;
			line-height: 60rpx;
		}
	}
}
.middle{
	height: 350rpx;
	width: 100%;
	margin-top: 65rpx;
	display: flex;
	flex-direction: column;
	.md1{
		font-size: 35rpx;
		font-weight: bold;
		color: #50d8be;
		margin-left: 25rpx;
	}
	.md2{
		height: 275rpx;
		width: 100%;
		margin-top: 30rpx;
		display: flex;
		padding: 0 100rpx 0 100rpx;
		justify-content: space-between;
		.md21{
			width: 220rpx;
			height: 275rpx;
			display: flex;
			flex-direction: column;
			text-align: center;
			.md211{
				margin-top: 50rpx;
				font-size: 120rpx;
			}
		}
		.md22{
			width: 220rpx;
			height: 275rpx;
			display: flex;
			flex-direction: column;
			text-align: center;
			.md221{
				margin-top: 50rpx;
				font-size: 120rpx;
			}
		}
	}
}
.pingjia{
	width: 100%;
	height: 430rpx;
	.pj1{
		font-size: 35rpx;
		font-weight: bold;
		color: #50d8be;
		margin-left: 25rpx;
	}
	.pj2{
		display: flex;
		.pj21,.pj22{
			height: 290rpx;
			font-size: 35rpx;
			display: flex;
			flex-direction: column;
			justify-content: space-evenly;
			margin-left: 100rpx;
		}
		.pj22{
			color: #50d8be;
			font-weight: bold;
		}
	}
}
.liaotian{
	width: 500rpx;
	height: 110rpx;
	background-color: #50d8be;
	border-radius: 30rpx;
	color: white;
	font-size: 50rpx;
	text-align: center;
	line-height: 110rpx;
	margin: 20rpx 130rpx;
	box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
}
</style>
