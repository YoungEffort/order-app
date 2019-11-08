<template>
	<view class="my-container">
		<view class="my-head">
			<image src="../../static/images/my-img.jpg" class="my-img" />
			<view class="my-user">
				<view class="my-user-name">王二娃子</view>
				<view>坑比前端</view>
			</view>
		</view>
		<view class="my-main">
			<view class="my-content">
				<view class="my-mgs">
					<view class="my-title">2019年11月08日</view>
					<view class="my-title-text">
						<view class="my-title-text-1">今日餐</view>
						<view>
							<view class="my-foot-row">一吃香1人餐</view>
							<view class="my-foot-row">一锅堂5人餐</view>
						</view>
					</view>
				</view>
			</view>
			<view class="my-operation">
				<view class="my-operation-row">
					<text>我的订单</text>
					<image src="../../static/images/icon-3.png" class="my-operation-arrow"/>
				</view>
				<view class="my-operation-row">
					<text>个人信息</text>
					<image src="../../static/images/icon-3.png" class="my-operation-arrow"/>
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
			
		}
	}
</script>

<style lang="less">
	.my-container{
		.my-head{
			position: relative;
			display: flex;
			align-items: center;
			flex-flow: row;
			// justify-content: space-between;
			padding: 20px 5% 80px;
			background:linear-gradient(180deg,rgba(68,179,225,1) 0%,rgba(60,170,220,1) 100%);
			.my-img{
				width: 80px;
				height: 80px;
				border-radius: 40px;
				box-shadow:0 0 10px rgba(0,0,0,.6) ;
			}
			.my-user{
				padding-left: 20px;
				font-size: 14px;
				color: #fff;
			}
			.my-user-name{
				padding-bottom: 10px;
			}
		}	
		
	}
	.my-main{
		position: relative;
		top: -60px;
		.my-content{
			margin: 0 auto;
			padding: 5% 5% 10px;
			width: 90%;
			border-radius: 10px 10px 0 0 ;
			background: #fff;
			.my-mgs{
				font-size: 14px;
				
			}
			.my-title{
				margin-bottom: 20px;
				padding-bottom: 6px;
				border-bottom: 1px solid #C0C0C0;
				text-align: center;
			}
			.my-title-text{
				display: flex;
				flex-flow: row nowrap;
			}
			.my-title-text-1{
				margin-right: 10px;
				font-size: 14px;
				font-weight: bold;
			}
			.my-foot-row{
				margin-bottom: 8px;
			}
		}
		.my-operation{
			margin-top: 14px;
			font-size: 14px;
			.my-operation-row{
				display: flex;
				justify-content: space-between;
				align-items: center;
				margin-bottom: 14px;
				padding: 10px 5%;
				background: #fff;
			}
			.my-operation-arrow{
				width: 16px;
				height: 12px;
			}
		}
	}
</style>
