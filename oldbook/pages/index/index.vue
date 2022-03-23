<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/logo.png" mode="widthFix" class="logo"></image>
				<view class="search" @click="toSearch">
					<image src="../../static/sousuo.png" mode="widthFix" class="search1"></image>
					<text>搜索商品名称</text>
				</view>
				<image src="../../static/xiaoxi.png" mode="widthFix" class="xiaoxi" @click="toMy"></image>
			</view>
		</view>


		<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="4000" :duration="400"
			indicator-color="rgba(255,255,255,.2)" indicator-active-color="rgba(255,255,255,.75)">
			<swiper-item v-for="(item,index) in swipers" :key="index">
				<image :src="item" mode="widthFix"></image>
			</swiper-item>
		</swiper>
		<view class="caidan">
			<view class="jiaocai">
				<image src="../../static/caidan/1.png" mode=""></image>
				<text class="txt">教辅教材</text>
			</view>
			<view class="wenxue">
				<image src="../../static/caidan/2.png" mode=""></image>
				<text class="txt">文学小说</text>
			</view>

			<view class="quanbu" @click="toAllsearch">
				<image src="../../static/caidan/3.png" mode=""></image>
				<text class="txt">全部分类</text>
			</view>

		</view>
		<view class="shudan" @click="toShudan">
			<text class="sd_txt">书单推荐</text>
			<view class="sd_img">
				<image src="../../static/caidan/4.png" mode=""></image>
			</view>
		</view>
		<view class="resou" @click="toResou">
			<text class="rs_txt">热搜榜单</text>
			<view class="rs_img">
				<image src="../../static/caidan/5.png" mode=""></image>
			</view>
		</view>
		<view class="xihuan">
			<text>猜你喜欢</text>
		</view>
		<view class="henxihuan">
			<view class="nixihuan" v-for="(item,index) in like" :key="index">
				<view class="n_img" @click="toXiangqing">
					<image :src="item.img" mode=""></image>
				</view>
				<view class="n_txt">
					<text class="n_txt1">{{item.name}}</text>
					<view class="n_txt2">
						<image src="../../static/xihuan/2.png" mode=""></image>
						<text class="n_txt21">{{item.biaoqian}}</text>
					</view>
					<view class="n_txt3">
						<image src="../../static/xihuan/3.png" mode=""></image>
						<text class="n_txt31">{{item.address}}</text>
					</view>
					<view class="n_txt4">
						<text class="n_txt41">￥{{item.newprice}}</text>
						<text class="n_txt42">￥{{item.oldprice}}</text>
						<image src="../../static/xihuan/4.png" mode=""></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: [
					require("@/static/dh/2.jpg"),
					require("@/static/dh/4.jpg"),
					require("@/static/dh/3.jpg"),
					require("@/static/dh/4.jpg"),
				],
				like: [{
						img: "../../static/xihuan/1.jpg",
						name: "沉默的大多数",
						biaoqian: "九成新",
						address: "西安科技大学",
						newprice: "16",
						oldprice: "22.6"
					},
					{
						img: "../../static/xihuan/1.jpg",
						name: "沉默的大多数",
						biaoqian: "九成新",
						address: "西安科技大学",
						newprice: "16",
						oldprice: "22.6"
					},
					{
						img: "../../static/xihuan/1.jpg",
						name: "沉默的大多数",
						biaoqian: "九成新",
						address: "西安科技大学",
						newprice: "16",
						oldprice: "22.6"
					},
					{
						img: "../../static/xihuan/1.jpg",
						name: "沉默的大多数",
						biaoqian: "九成新",
						address: "西安科技大学",
						newprice: "16",
						oldprice: "22.6"
					}
				],

			}
		},
		onLoad() {

		},
		methods: {
			toSearch() {
				uni.navigateTo({
					url: "./find"
				})
			},
			toAllsearch() {
				uni.navigateTo({
					url: "./allsearch"
				})
			},
			toShudan() {
				uni.navigateTo({
					url: "./shudan"
				})
			},
			toResou() {
				uni.navigateTo({
					url: "./resou"
				})
			},
			toMy(){
				
			},
			toXiangqing(){
				uni.navigateTo({
					url: "./xiangqing"
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

	.head_bg {
		width: 100%;
		background-color: #50d8be;
		z-index: 100;
		position: fixed;
		left: 0;
		top: 0;

		.head {
			display: flex;
			align-items: center;
			box-sizing: border-box;
			height: 80rpx;
			/* #ifdef MP-WEIXIN */
			width: calc(100% - 95px);
			/* #endif */
			/* #ifndef MP-WEIXIN */
			width: 100%;
			/* #endif */
			.logo {
				width: 50rpx;
				height: 33rpx;
				margin: 0 26rpx;
			}

			.search {
				flex-grow: 1;
				height: 64rpx;
				border: 1px #e6e6e6 solid;
				background-color: white;
				display: flex;
				align-items: center;
				border-radius: 10rpx;
				color: #c1c1c1;

				.search1 {
					width: 27rpx;
					height: 27rpx;
					margin: 0 15rpx;
				}
			}

			.xiaoxi {
				width: 38rpx;
				height: 37rpx;
				margin: 0 33rpx;
			}
		}
	}

	.swiper {
		background-color: #fff;
		height: 360rpx;
		margin: 170rpx 20rpx 20rpx 20rpx;

		swiper-item {
			width: 100%;
			height: 100%;

			image {
				width: 100%;
				height: 100%;
			}
		}
	}

	.caidan {
		width: 680rpx;
		height: 200rpx;
		margin: 50rpx auto;
		background-color: #ffffff;
		border: 6rpx #c0c0c0 solid;
		border-radius: 30rpx;
		display: flex;
		justify-content: space-around;
		align-items: center;

		.jiaocai {
			width: 120rpx;
			height: 145rpx;

			image {
				width: 120rpx;
				height: 88rpx;
			}
		}

		.wenxue {
			width: 120rpx;
			height: 145rpx;

			image {
				width: 120rpx;
				height: 88rpx;
			}
		}

		.quanbu {
			width: 120rpx;
			height: 145rpx;

			image {
				width: 120rpx;
				height: 88rpx;
			}
		}

		.txt {
			font-size: 25rpx;
			margin: 0 auto;
		}
	}

	.shudan {
		width: 680rpx;
		height: 250rpx;
		border-radius: 20rpx;
		display: flex;
		background-color: #edf1f2;
		margin: 15rpx auto;
		position: relative;

		.sd_txt {
			position: absolute;
			top: 45rpx;
			left: 70rpx;
			font-size: 45rpx;
			color: #50d8be;
		}

		image {
			width: 375rpx;
			height: 240rpx;
			position: absolute;
			right: 30rpx;
			top: 10rpx;

		}
	}

	.resou {
		width: 680rpx;
		height: 250rpx;
		border-radius: 20rpx;
		display: flex;
		background-color: #edf1f2;
		margin: 15rpx auto;
		position: relative;

		.rs_txt {
			position: absolute;
			top: 45rpx;
			left: 70rpx;
			font-size: 45rpx;
			color: #50d8be;
		}

		image {
			width: 375rpx;
			height: 240rpx;
			position: absolute;
			right: 30rpx;
			top: 10rpx;

		}
	}

	.xihuan {
		height: 110rpx;
		width: 160rpx;
		font-size: 38rpx;
		font-weight: bold;
		margin-left: 35rpx;
		line-height: 110rpx;
	}

	.henxihuan {
		flex-wrap: wrap;
		width: 100%;
		display: flex;

		.nixihuan {
			width: 320rpx;
			height: 520rpx;
			border: 6rpx #c0c0c0 solid;
			border-radius: 20rpx;
			flex-direction: column;
			background-color: #ffffff;
			margin: 15rpx 15rpx 15rpx 25rpx;
			display: flex;
			flex-wrap: wrap;
			position: relative;

			.n_img {
				height: 315rpx;
				width: 100%;

				image {
					width: 220rpx;
					height: 315rpx;
					margin: 0 50rpx;
				}
			}

			.n_txt {
				height: 205rpx;
				width: 100%;
				background-color: #edf1f2;
				border-radius: 0 0 20rpx 20rpx;
				position: absolute;
				bottom: 0;

				.n_txt1 {
					color: #acb0b2;
					font-size: 27rpx;
					margin-left: 24rpx;
					margin-top: 20rpx;
				}

				.n_txt2 {
					height: 50rpx;
					width: 100%;
					padding-left: 23rpx;
					padding-top: 20rpx;

					image {
						width: 30rpx;
						height: 30rpx;
					}

					.n_txt21 {
						font-size: 23rpx;
						color: #acb0b2;
						margin-bottom: 5rpx;
						margin-left: 20rpx;
					}
				}

				.n_txt3 {
					height: 40rpx;
					width: 100%;
					padding-left: 23rpx;
					padding-top: 10rpx;

					image {
						width: 30rpx;
						height: 30rpx;
					}

					.n_txt31 {
						font-size: 23rpx;
						color: #acb0b2;
						margin-left: 25rpx;
					}
				}

				.n_txt4 {
					height: 70rpx;

					.n_txt41 {
						font-size: 33rpx;
						color: #50d8be;
						margin-left: 30rpx;
						font-weight: bold;
					}

					.n_txt42 {
						font-size: 15rpx;
						color: #000000;
						text-decoration: line-through;
						margin-left: 22rpx;
					}

					image {
						width: 42rpx;
						height: 42rpx;
						margin-left: 55rpx;
					}
				}
			}
		}
	}
</style>
