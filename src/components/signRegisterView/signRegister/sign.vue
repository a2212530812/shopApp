<template>
	<div>
		<div class="box show">
			<p><input type="tel" :class="{red:isred}" v-model="phone" @focus="zz" placeholder="请输入手机号"><img src="../../../assets/images/icon1.jpg"></p>
			<p><input type="text" placeholder="请输入密码"><img src="../../../assets/images/icon2.jpg"></p>
			<p><button @click="checkMobile()">登录</button></p>
			<p class="fogetpwd">
				<router-link to='/forgetPwd/1'>忘记密码？</router-link>
			</p>
		</div>
	</div>
</template>

<script>
	export default {

		data() {
			return {
              phone: "",
              isred:false
			}
		},
		methods: {
			checkMobile() {
				if(!(/^1[3|4|5|8][0-9]\d{4,8}$/.test(this.phone))) {
					this.phone="请输入正确的手机号";
					//document.mobileform.mobile.focus();
					this.isred=true;
					return false;
				}
			},
			zz(){
				this.phone=""
				this.isred=false;
			}
		},

	}
</script>

<style scoped="scoped">
	.box {
		width: 100%;
	}
	
	.box p {
		width: 90%;
		margin: 10px 5% 0;
		position: relative;
		line-height: 40px;
		height: 40px;
		padding: 5px 0;
		text-align: center;
	}
	
	input {
		border: none;
		border-bottom: 1px solid #dddddd;
		width: 100%;
		height: 100%;
		line-height: 100%;
		text-align: center;
	}
	.red{
		color: red;
	}
	.box p img {
		position: absolute;
		left: 0;
		top: 10px;
		height: 30px;
	}
	
	button {
		width: 90%;
		margin: 0 5%;
		background: #ca3232;
		color: white;
		border: none;
		border-radius: 4px;
		line-height: 40px;
	}
	
	#zhuce input {
		text-align: left;
		box-sizing: border-box;
		padding-left: 15%;
	}
	
	.fogetpwd {
		font-size: 12px;
	}
</style>