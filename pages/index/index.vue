<style lang="scss">
	.header_search{
		border: solid 1px #f55056;
	}
	.container {
		background-color: #f6f6f6;
		min-height: 200vh;
	}
	.swiper-item image{
		width: 100%;
		height: 350rpx;
	}
	.swiper{
		height: 350rpx;
		
	}
	.banner_img{
		width: 100%;
	}
	.index_header{
		width: 100%;
		padding: 8rpx 10rpx;
		background-color: #efeff4;
	}
	.sears_header{
		width: 100%;
		padding: 16rpx 20rpx;
		
	}
	.none_search{
		background-color: #ffffff;
	}
	.table_barts ul{
		padding: 40rpx;
		display: flex;
		justify-content: space-between;
		li{
			display: flex;
			flex-direction: column;
			align-items: center;
		}
		image{
			width: 104rpx;
			height: 104rpx;
		}
		span{
			font-size: 22rpx;
			margin-top: 20rpx;
		}
	}
	.header_height{
		   height: var(--status-bar-height);
		    width: 100%;
	}
	
</style>

<template>
	<view class="container">
<!-- 		<view class="header_height"></view>
		<view class="sears_header">
			<view class="none_search">
				<uni-icons type="search" size="30"></uni-icons>
				<input type="text" value="" />
			</view>
		</view> -->
		<view class="uni-padding-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<swiper class="swiper" :indicator-dots="true" :autoplay="false" :interval="3000" :circular="true">
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image class="banner_img" src="@/static/image/ban1.jpg" alt="">
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image class="banner_img" src="@/static/image/ban2.jpg" alt="">
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image class="banner_img" src="@/static/image/ban3.jpg" alt="">
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image class="banner_img" src="@/static/image/ban4.jpg" alt="">
							</view>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>
		<view class="table_barts">
			<ul>
				<li>
					<image src="@/static/image/icon-link1.png" mode=""></image>
					<span>精选推荐</span>
				</li>
				<li>
					<image src="@/static/image/icon-link2.png" mode=""></image>
					<span>酒水专场</span>
				</li>
				<li>
					<image src="@/static/image/icon-link3.png" mode=""></image>
					<span>订单管理</span>
				</li>
				<li @click="_toPricess">
					<image src="@/static/image/icon-link4.png" mode=""></image>
					<span>商家入驻</span>
				</li>
			</ul>
		</view>
	</view>
</template>

<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		data() {
			return {

			}
		},
		onLoad() {
			uni.getProvider({
			    service: 'payment',
			    success: function (res) {
					console.log(res)
			    }
			
			});
		},
		onShow(){
			console.log("触发了")
		},
		onReachBottom(){
			console.log("滚动到底部了")
		},
		onNavigationBarSearchInputChanged(){
			console.log("输入内容变化了")
		},
		onNavigationBarButtonTap(obj){
			console.log(obj)
			console.log("点击了导航的分享按钮")
		},
		onNavigationBarSearchInputConfirmed(){
			console.log("点击了软键盘的搜索")
		},
		
		
		
		methods: {
			_toPricess(){
				// uni.switchTab({
				//     url: '/pages/classify/classify'
				// });
				
				
				// 支付
				// uni.requestPayment({
				//     provider: 'alipay',
				//     orderInfo:"orderInfo",
				//     success: function (res) {
				//         console.log('success:' + JSON.stringify(res));
				//     },
				//     fail: function (err) {
				//        uni.showModal({
				//            title: '提示',
				//            content: '这是一个模态弹窗',
				//            success: function (res) {
				//                if (res.confirm) {
				//                    console.log('用户点击确定');
				//                } else if (res.cancel) {
				//                    console.log('用户点击取消');
				//                }
				//            }
				//        });
				//     }
				// });
				
				// 页面跳转(保存当前页面)
				// uni.navigateTo({ url: '/pages/process/process'})
			},
		},
		
		components: {
			uniNavBar,
			uniIcons
		}
	}
</script>
