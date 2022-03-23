<template>
	<view>
		<view class="maininterface">

			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>

			<view class="maintop">
				<!-- 导航栏 -->
				<image src="../../static/bookcircle/remove.png" mode="widthFix" @click="remove"></image>
				<text class="txt">我的收藏</text>
				<image src="../../static/bookcircle/star.png" mode="widthFix"></image>
			</view>
           
		   
		   <view class="making">
		   	<text>正在抓紧制作中👀</text>
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
			remove() {
				uni.switchTab({
					url: "./book-circle"
				})
			}
		}
	}
</script>

<style lang="scss">
	.maininterface {
		.status_bar {
			height: var(--status-bar-height);
			width: 100%;
		}

		.maintop {

			height: 80rpx;
			box-sizing: border-box;
			width: 100%;
			background-color: #50d8be;
			/* #ifdef MP-WEIXIN */
			//解决微信小程序的胶囊问题
			width: calc(100% - 95px);
			/* #endif */
			/* #ifndef MP-WEIXIN*/
			width: 100%;
			display: flex;

			/* #endif*/
			.txt {
				margin: 18rpx 0 0 240rpx;
				font-size: 35rpx;
				font-weight: bold;
				color: white;
			}


			image:nth-child(1) {
				height: 45rpx;
				width: 45rpx;
				margin-top: 15rpx;

			}

			image:nth-child(3) {
				height: 45rpx;
				width: 45rpx;
				margin: 18rpx 0 0 15rpx;
			}

		}
		.making{
			background-color: #8a8a8a;
			width: 100%;
			height: 600rpx;
			margin-top: 300rpx;
			text-align: center;
			line-height: 600rpx;
			text{
				color: red;
				font-weight: bold;
				font-size: 50rpx;
			}
		}
	}
</style>
