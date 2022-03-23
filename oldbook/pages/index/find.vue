<template>
	<view>
		<view class="head_bg">
		<view class="status_bar">
		  <!-- 这里是状态栏 -->
		</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<input type="text" value="" placeholder="输入商品名称" class="input"/>
				<view class="ss">
					<text class="ss1">搜索</text>
				</view>
			</view>
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
			uni.switchTab({
				url:"./index"
			});
		}			
		}
	}
</script>

<style lang="scss">
.status_bar {
			height: var(--status-bar-height);
			width: 100%;
}
.head_bg{
	background-color: #999999;
	height: 100rpx;
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	.head{
		/* #ifdef MP-WEIXIN */
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN */
		width: 100%;
		/* #endif */
		background-color: #999999;
		border-radius: 0 0 50rpx 50rpx;
		width: 750rpx;
		height: 100rpx;
		display: flex;
		position: relative;
		image{
				height: 38rpx;
				width: 38rpx;
				margin-left: 35rpx;
				margin-top: 30rpx;
		}
		.input{
			width: 600rpx;
			height: 80rpx;
			background-color: red;
			margin:10rpx 10rpx 10rpx 30rpx;
			border-radius: 25rpx;
			padding-left: 15rpx;
			background-color: #ffffff;
		}
		.ss{
			position: absolute;
			top: 20rpx;
			right: 40rpx;
			width: 120rpx;
			height: 60rpx;
			background-color: #50d8be;
			border-radius: 20rpx;
			text-align: center;
			.ss1{
				font-size: 35rpx;
				color: white;
				line-height: 60rpx;
			}
		}
	}
}
</style>
