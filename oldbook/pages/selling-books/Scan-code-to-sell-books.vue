<template>
	<view>
		<view class="navigate">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/bookcircle/remove.png" mode="widthFix" @click="remove"></image>
				<text>扫码卖书</text>
			</view>
		</view>
		<view class="mainbody">
			<image src="../../static/22.png" mode="widthFix"></image>
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
					url:"./selling-books"
				})
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
		.head {
			/* #ifdef MP-WEIXIN */
			//解决微信小程序的胶囊问题
			width: calc(100% - 95px);
			/* #endif */
			/* #ifndef MP-WEIXIN*/
			width: 100%;
			/* #endif*/
			height: 80rpx;
			background-color: #50d8be;

			image {
				height: 45rpx;
				width: 45rpx;
				margin-top: 15rpx;
			}

			text {
				margin: 18rpx 0 0 240rpx;
				font-size: 35rpx;
				font-weight: bold;
				color: white;
			}
		}
	}
	.mainbody{
		width: 100%;
		height: 1000rpx;
		display: flex;
		align-items: center;
		justify-content: space-around;
		image{
			height: 600rpx;
			width: 600rpx;
		}
		
	}
</style>
