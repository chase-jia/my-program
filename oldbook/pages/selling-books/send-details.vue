<template>
	<view>
		<view class="navigate">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/bookcircle/remove.png" mode="widthFix" @click="remove"></image>
				<text>详细信息</text>
			</view>
		</view>

		<view class="logo">
			<image src="../../static/otherphoto/logo.png" mode="widthFix"></image>
		</view>

		<view class="mainbody">
			<view class="special-case" v-for="(item,index) in specialdetailsList" :key="index">
				<text>{{item.bookdetail}}</text>
				<input type="text" value="" class="fillin" focus="false" />

			</view>
		</view>

		<!-- <view class="">
			
		</view> -->






		<view class="footer">
			<u-button type="default" class="btn" shape="square" size="medium" @click="changeissure">确认</u-button>
		</view>

		<j-pop @replace="replace" @replace1="replace1" :issure="issure"></j-pop> <!-- 自定义组件 -->


	</view>
</template>

<script>
	export default {
		data() {
			return {
				specialdetailsList: [{
					bookdetail: "书籍类型:",
				}, {
					bookdetail: "书籍名称:",
				}, {
					bookdetail: "出版日期:",
				}, {
					bookdetail: "购买时间:",
				}, {
					bookdetail: "预售价格:",
				}, {
					bookdetail: "实际价格:"
				}],
				issure: false,




			}
		},
		methods: {
			remove() {
				uni.switchTab({
					url: "./selling-books"
				})
			},
			changeissure() {
				this.issure = true;

			},
			replace() {
				this.issure = false;
				uni.switchTab({
					url: "./selling-books"
				})


			},
			replace1() {
				this.issure = false;

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

	.logo {
		height: 200rpx;
		width: 100%;
		box-sizing: border-box;

		image {
			width: 200rpx;
			height: 200rpx;
			margin-left: 20rpx;
		}
	}

	.mainbody {

		margin: 40rpx 10% 0 10%;
		height: 600rpx;
		width: 80%;

		.special-case {
			display: flex;
			width: 100%;
			height: 100rpx;
			justify-content: space-around;
			align-items: center;

			.fillin {
				border: 1rpx #50d8be solid;
				width: 50%;
			}
		}

	}

	.footer {
		margin-top: 100rpx;
		display: flex;
		width: 100%;
		justify-content: space-around;

	}
</style>
