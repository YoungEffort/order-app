<template>
	<view class="content">
		<view class="head">
			<switch checked class="p-left" />
			<text class="title">我的加班餐</text> 
		</view>
		<view class="box">
			<view class="item-1">11</view>
			<view class="item-2">22</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		width:100%;
		height:100%;
	}

	.head {
		display: flex;
		justify-content: center;
		height: 40px;
		line-height: 40px;
		font-size: 18px;
		border: 1px solid #FBFBFB;
	}
	
	.p-left {
		position: absolute;
		left: 0;
	}

	.box {
		height:100%;
		display: flex;
	}

	.item-1 {
		width:17%;
	}

	.item-2 {
		width:83%;
		height:100%;
		background:#F8F8F8;
		padding:5px;
	}
</style>
