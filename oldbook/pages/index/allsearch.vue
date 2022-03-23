<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">全部分类</text>
			</view>
		</view>
		<view class="page">
			<view class="left">
				<scroll-view scroll-y="true" style="height: 100%;">
					<view v-for="(item,index) in menu" :key="index" class="item"
					:class="{'active':index==choose}" @click="changeChoose(index)">{{item}}</view>
				</scroll-view>
			</view>
			<view class="right">
				<scroll-view scroll-y="true" style="height: 100%;" :scroll-into-view="whichId"
				:scroll-with-animation="true">
					<view class="" v-for="(item,index) in goods_list" :key="index">
						<text class="title" :id="item.id">{{item.name}}</text>
						<view class="">
							<view class="good_item" v-for="(goodsItem,goodsIndex) in item.list" 
							:key="goodsIndex" @click="toDetail(goodsItem.id)">
								<image :src="goodsItem.pic" class="good_img"></image>
								<view class="">
									<view class="name">
										{{goodsItem.name}}
									</view>
									<view class="price">
										{{goodsItem.zuozhe}}
									</view>
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menu:["教材教辅","文学小说","经管励志","人文社科","生活艺术","计算机能","职业技能"],
				choose:0,
				whichId:"g0",
				goods_list:[
					{
						id:"g0",
						name:"教材教辅",
						list:[
							{
								id:"0",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"1",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"2",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"3",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g1",
						name:"文学小说",
						list:[
							{
								id:"4",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"5",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"6",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"7",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g2",
						name:"经管励志",
						list:[
							{
								id:"8",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"9",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"10",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"11",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g3",
						name:"人文社科",
						list:[
							{
								id:"12",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"13",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"14",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"15",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g4",
						name:"生活艺术",
						list:[
{
								id:"16",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"17",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"18",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"19",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g5",
						name:"计算机能",
						list:[
							{
								id:"20",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"21",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"22",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"23",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},{
						id:"g6",
						name:"职业技能",
						list:[
							{
								id:"24",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"25",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"26",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							},{
								id:"27",
								name:"沉默的大多数",
								zuozhe:"王小波",
								pic:"../../static/xihuan/1.jpg"
							}
						]
					},
				]
			}
		},
		methods: {
			toSearch(){
				uni.navigateTo({
					url:"../index/find"
				})
			},
			toDetail(id){
				uni.navigateTo({
					url:"detail?id="+id
				})
			},
			changeChoose(i){
				this.choose = i;
				this.whichId = "g"+i;
			},
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
.page{
	margin-top: 180rpx;
	display: flex;
	height: calc(100vh - 10rpx);
	overflow: hidden;
	.left{
		width: 170rpx;
		height: 100%;
		.item{
			height: 30rpx;
			line-height: 30rpx;
			font-size: 26rpx;
			margin: 68rpx 0;
			text-align: center;
			position: relative;
			&.active{
				font-weight: bold;
				&::before{
					display: block;
					content: "";
					width: 8rpx;
					height: 100%;
					background-color: #50d8be;
					position: absolute;
					left: 0;
					top: 0;
				}
			}
		}
	}
	.right{
		flex: 1;
		padding-left:20rpx;
		padding-right: 40rpx;
		box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
		.title{
			display: block;
			font-size: 32rpx;
			font-weight: bold;
		}
		.good_item{
			display: flex;
			background-color: #f7f7f7;
			box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
			border-radius: 10rpx;
			height: 150rpx;
			padding: 25rpx 30rpx;
			box-sizing: border-box;
			line-height: 55rpx;
			font-size: 28rpx;
			margin-bottom: 15rpx;
			.good_img{
				width: 83rpx;
				height: 110rpx;
				margin-right: 35rpx;
				box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
			}
		}
		
	}
}

</style>

