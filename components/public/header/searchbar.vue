<template>
	<div class="search-panel">
		<el-row class="m-header-searchbar">
			<el-col :span="3" class="left">
				<img src="https://s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png"
						 alt="">
			</el-col>
			<el-col :span="15" class="center">
				<div class="wrapper">
					<el-input v-model="search" placeholder="搜索商家或地点" @focus="focus()" @blur="blur()"/>
					<button class="el-button el-button--primary"><i class="el-icon-search"></i></button>
					<dl class="hotPlace" v-if="isHotPlace">
						<dt>热门搜索</dt>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
					</dl>
					<dl class="searchList" v-if="isSearchList">
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
						<dd>火锅</dd>
					</dl>
				</div>
				<p class="suggset">
					<a href="#">故宫博物院</a>
					<a href="#">故宫博物院</a>
					<a href="#">故宫博物院</a>
					<a href="#">故宫博物院</a>
					<a href="#">故宫博物院</a>
					<a href="#">故宫博物院</a>
				</p>
				<ul class="nav">
					<li>
						<nuxt-link to="/" class="takeout">美团外卖</nuxt-link>
					</li>
					<li>
						<nuxt-link to="/" class="movie">猫眼电影</nuxt-link>
					</li>
					<li>
						<nuxt-link to="/" class="hotel">美团酒店</nuxt-link>
					</li>
					<li>
						<nuxt-link to="/" class="apartment">民宿</nuxt-link>
					</li>
					<li>
						<nuxt-link to="/" class="business">商家入驻</nuxt-link>
					</li>
				</ul>
			</el-col>
			<el-col :span="6" class="right">
				<ul class="security">
					<li><i class="refund"></i>
						<p class="txt">随时退</p></li>
					<li><i class="single"></i>
						<p class="txt">随时退</p></li>
					<li><i class="overdue"></i>
						<p class="txt">随时退</p></li>
				</ul>
			</el-col>
		</el-row>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				isFocus: false,
				search: '',
				hotPlace:[],
				searchList:[],
			}
		},
		computed: {
			isHotPlace() {
				return this.isFocus && !this.search
			},
			isSearchList() {
				return this.isFocus && this.search
			}
		},
		methods: {
			focus() {
				this.isFocus = true
			},
			blur() {
				let self = this
				setTimeout(function () {
					self.isFocus = false
				}, 200)
			}
		}
	}
</script>

<style scoped>
</style>
