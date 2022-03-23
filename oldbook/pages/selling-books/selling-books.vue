<template>
	<view>
		<scroll-view scroll-y="true">
			<view class="nivagate">
				<view class="status_bar">
					<!-- 这里是状态栏 -->
				</view>
				<view class="head">
					<text>卖书</text>
				</view>
			</view>
			<view class="mainbody" v-for="(item,index) in List" :key="index">
				<text class="txt1">{{item.number}}</text>
				<text class="txt2" @click="tonewpage(item.id)">{{item.font}}</text>
				<image :src="item.src" mode="widthFix" class="img"></image>
			</view>

			<view class="footer">
				<u-button type="info" shape="square" size="medium" @click="tosellbook">扫码卖书</u-button>
				<u-button type="info" shape="square" size="medium" @click="tofillin">确认出售</u-button>
			</view>

			<j-pop @replace="replace" @replace1="replace1" :issure="issure"></j-pop> <!-- 自定义组件 -->
		</scroll-view>




	</view>
</template>

<script>
	export default {
		data() {
			return {
				List: [{
					id: 1,
					number: "1",
					font: "填写信息",
					src: "../../static/seelingbook/message.png"
				}, {
					id: 2,
					number: "2",
					font: "书籍详情",
					src: "../../static/seelingbook/receive.png"
				}, {
					id: 3,
					number: "3",
					font: "售卖信息",
					src: "../../static/seelingbook/send.png"
				}],
				issure: false,
			}
		},
		methods: {
			tonewpage(parameter) {
				if (parameter == 1) {
					uni.navigateTo({
						url: "./fill-in-message"
					})
				} else if (parameter == 2) {
					uni.navigateTo({
						url: "./send-details"
					})
				} else {
					uni.navigateTo({
						url: "./receicve-payment"
					})
				}
			},
			tosellbook() {
				uni.navigateTo({
					url: "./Scan-code-to-sell-books"
				})
			},
			tofillin() {
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

	.nivagate {
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
			align-items: center;
			justify-content: space-around;

			text {
				height: 60rpx;
				width: 60rpx;
				color: white;
			}
		}

	}

	.mainbody {
		margin-top: 150rpx;
		height: 300rpx;
		display: flex;
		box-sizing: border-box;

		.txt1 {
			// margin-top: 60rpx;
			margin-left: 30rpx;
			color: red;
			font-size: bold;
			font-style: oblique;
			font-size: 35rpx;
		}

		.txt2 {
			// margin-top:60 rpx;
			margin-left: 30rpx;
			color: red;
			font-size: bold;
			font-style: oblique;
			font-size: 35rpx;
		}



		.img {
			width: 300rpx;
			height: 220rpx;
			margin-top: 50rpx;
			margin-left: 180rpx;
		}
	}

	.footer {
		margin-top: 70rpx;
		display: flex;
		justify-content: space-around;
	}
</style>
