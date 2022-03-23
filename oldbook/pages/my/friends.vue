<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			    <!-- 这里是状态栏 -->
			   </view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhuimy(syy)"></image>
				<view class="zi">好友列表</view>
			</view>
		</view>
		<view class="gd">
			<u-index-list :scrollTop="scrollTop"  offset-top="140" z-index="1" activeColor="#50d8be" sticky="false">
						<view v-for="(item, index) in indexList" :key="index">
							<u-index-anchor :index="item"/>
								<view class="list-cell" v-for="(item,index) in friendlist" :key="index">
									<image src="../../static/shu/1.png" mode="" class="_l" @click="fanhuimy(item)"></image>
									<text class="name">{{item.name}}</text>
								</view>
						</view>
			</u-index-list>
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
				scrollTop: 0,
				indexList: ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U","V", "W", "X", "Y", "Z"],
				friendlist:[{   //每个字母下的列表
					name:"巴扎黑",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				},{
					name:"贾浩鹏",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				},{
					name:"贾浩鹏",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				}],
				allfriend:[{  //所有好友的列表，在这里筛选完之后再添加到friends里
					name:"巴扎黑",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				},{
					name:"贾浩鹏",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				},{
					name:"李佳蓉",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				},{
					name:"赵文华",
					src:"../../static/shu/1.png",
					url:"../../pages/my/my",
					newurl:"../../pages/my/xiaoxi"
				}]
			}
		},
		onPageScroll(e) {
					this.scrollTop = e.scrollTop;
				},
		methods: {
			fanhuimy(e){
				uni.switchTab({
					url: e.url
				})
			},
		}
	}
</script>

<style lang="scss">
	.gd{
		// margin-top: 140upx;
		height: 20upx;
		width: 100%;
		background-color: #000000;
		box-sizing: border-box;
		line-height: 20upx;
		.name{
			color: #50d8be;
			font-size: 30upx;
			justify-content: space-evenly;
			padding-top: 35upx;
			text-align: center;
		}
		._l{
			display:flex;//弹性模型
			width: 100upx;
			height: 100upx;
			border-radius: 50upx;
		}
		._r{
			display:flex;//弹性模型
			width: 50upx;
			height: 50upx;
			border-radius: 50upx;
		}
	}
	.list-cell {
			display: flex;
			box-sizing: border-box;
			width: 100%;
			padding: 10px 24rpx;
			overflow: hidden;
			color: #323233;
			font-size: 14px;
			line-height: 24px;
			background-color: #fff;
		}
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
			height:70upx;
			background-color: #50d8be;
			display: flex;//弹性布局
			align-items: center;
			.jt{
				width: 45upx;
				height: 45upx;
				margin-left: 50upx;
				font-size: 45upx;
				
			}
			.zi{
				color: #393939;
				font-size: 45upx;
				border-bottom: 6upx #FFFFFF solid;
				font-weight: bold;
				margin-left:190upx;
			}
		}
	}
</style>
