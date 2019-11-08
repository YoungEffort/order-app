<template>
	<view class="personal">
		<form @submit="formSubmit">
			<view class="personal-row">
			   <view class="personal-lable">姓名</view>
			   <input name="input" placeholder="请输入姓名" class="personal-input"/>
			</view>
			<view class="personal-row" @click="showPicker">
				<view class="personal-lable">组织</view>
				<view class="personal-input">
					<text class="placeholder-text" v-show="!pickerText">请选择</text>
					<text class="placeholder-value" v-show="pickerText">{{pickerText}}</text>
				</view>
			</view>
			<button form-type="submit" class="personal-submit">完成</button>
		</form>
		
		 <mpvue-picker ref="mpvuePicker" 
			className = 'mpvue-picker-container'
			mode="multiLinkageSelector"
			:pickerValueArray="pickerValueArray" 
			:pickerValueDefault='pickerValueDefault' 
			@onConfirm="onConfirm" 
		 />
	</view>
</template>

<script>
	import { MpvuePicker } from '../../components/index.js'
	export default {
		components:{
			MpvuePicker
		},
		data() {
			return {
				// 个人信息
				personalData: {
					name: '',
					worker: ''
				},
				// 组织二级联动选择数据
				pickerValueArray: [
					{
						label: '技术中心',
						value: 0,
						children: [
							{
								label: '产品',
								value: 1,
							},
							{
								label: '产品助理',
								value: 2,
							},
							{
								label: 'java工程师',
								value: 3,
							}
						]
					},
					{
						label: '人资行政',
						value: 1,
						children: [
							{
								label: '前台',
								value: 1,
							},
							{
								label: 'HR',
								value: 2,
							},
							{
								label: '人事主管',
								value: 3,
							}
						]
					}
				],
				// 初始选中下标
				pickerValueDefault: [0, 0],
				// 选中的值
				pickerText: '',
				pickerCode: ''
			}
		},
		methods: {
			// 表单数据获取
			formSubmit(e) {
			   console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e.detail.value))        
			},
			// 组织选择联动显示
			showPicker() {
			   this.$refs.mpvuePicker.show();
			},
			// 选择组织
			onConfirm(e) {
				let text = e.label.split('-')
				this.pickerText = text[0] + ' / ' + text[1]
			}
		}
	}
</script>

<style lang="less">
	.personal{
		padding-top: 10px;
		.personal-row{
			margin-bottom:20px ;
		}
		.personal-lable{
			padding: 4px 5%;
			font-size: 12px;
			color: #999;
		}
		.personal-input{
			padding: 10px 5%;
			border-top: 1px solid #d9d9d9;
			border-bottom: 1px solid #d9d9d9;
			background: #fff;
			font-size: 14px;
		}
		.placeholder-text{
			color: grey;
		}
		.placeholder-value{
			color: inherit;
		}
		.personal-submit{
			margin: 50px auto 0;
			width: 90%;
			border: none;
			background: #44B3E1;
			font-size: 16px;
			color: #fff;
		}
		.personal-submit:after{
			display: none;
		}
	}
</style>
