<template>
	<div class="foo">
		<header>
			<button @click="onClick">押して</button>
			<input type="radio" id="one" value="slide" v-model="picked"/>
			<label for="one">スライド</label>
			<input type="radio" id="two" value="axis1" v-model="picked"/>
			<label for="two">１軸回転</label>
			<input type="radio" id="three" value="axis3" v-model="picked"/>
			<label for="three">３軸回転</label>
			<span>Picked: {{ picked }}</span>
			<h1>header</h1>
		</header>
		<div class="holyGrail">
			<main class="content">
			<div class="watson-base" ref="watson" :class="zwatson">わとそん<br/>あいうえお<br/>あいうえお<br/>あいうえお</div>
			<div class="user-base" ref="user" :class="zuser">ゆーざー<br/>１２３４５<br/>１２３４５<br/>１２３４５</div>
			</main>
			<nav class="side-nav">
				<img class="gazo" src="../assets/logo.png"/>
				<ul>
					<li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
					<li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
					<li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
					<li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
				</ul>
				<h2>Ecosystem</h2>
				<ul>
					<li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
					<li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
					<li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
					<li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
					<br>
					<li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
				</ul>
				<h2>Essential Links</h2>
				<h1>{{ msg }}</h1>
			</nav>
		</div>
		<footer>
			<h1>footer</h1>
		</footer>
	</div>
</template>

<script>
import Vue from 'vue';
export default {
	name: 'Foo',
	data () {
		return {
			zwatson:'temae-slide',
			zuser:'oku-slide',
			picked: 'slide',
			arr:[],
			msg: 'Welcome to Your Vue.js App'
		}
	},
	methods:{
		onClick: function(e){
			//console.log(this.$refs.watson.style['z-index']);
			if( this.zwatson.lastIndexOf('temae', 0) === 0 ){
				this.zwatson = 'oku-' + this.picked;
				this.zuser = 'temae-' + this.picked;
			}else{
				this.zwatson = 'temae-' + this.picked;
				this.zuser = 'oku-' + this.picked;
			}
			//this.arr.unshift(new Date());
			//Vue.nextTick(() => window.scrollTo(this.$refs.list.scrollHeight,0));
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.temae-slide {
	z-index:0;
	transition: all 0.5s cubic-bezier(.5,-2.0,.5,2.0);
	//transition: all 0.5s cubic-bezier(.68,-0.55,.26,1.55);
	transform: translate(0, 5em);
}
.oku-slide {
	z-index:1;
	transition: all 0.5s cubic-bezier(.5,-2.0,.5,2.0);
	//transition: all 0.5s cubic-bezier(.68,-0.55,.26,1.55);
	transform: translate(0, 0);
}
.temae-axis1 {
	z-index:0;
	transition: all 0.5s ease-in-out;
	transform: translate(0, 5em) rotateX(360deg) rotateY(0deg) rotateZ(0deg);
}
.oku-axis1 {
	z-index:1;
	transition: all 0.5s ease-in-out;
	transform: translate(0, 0) rotateX(0deg) rotateY(0deg) rotateZ(0deg);
}
.temae-axis3 {
	z-index:0;
	transition: all 0.5s ease-in-out;
	transform: translate(0, 5em) rotateX(180deg) rotateY(180deg) rotateZ(180deg);
}
.oku-axis3 {
	z-index:1;
	transition: all 0.5s ease-in-out;
	transform: translate(0, 0) rotateX(0deg) rotateY(0deg) rotateZ(0deg);
}
.watson-base {
	color:white;
	position:absolute;
	border: solid 1px red;
	border-radius: 20px;
	background-color: rgba(255,0,0,0.8);
	margin:{
		top:0.5em;
		bottom:0.5em;
		left:0.5em;
	};
	padding: {
		top: 2em;
		bottom: 2em;
	};
	width:75%;
}
.user-base {
	color:white;
	position:absolute;
	border: solid 1px blue;
	border-radius: 20px;
	background-color: rgba(0,0,255,0.8);
	margin:{
		top:0.5em;
		bottom:0.5em;
		left:10%;
	};
	padding: {
		top:2em;
		bottom:2em;
		right:0.5em;
	};
	width:75%;
}
.foo {
  display: flex;
  height: 100vh;
  flex-direction: column;
}

header, footer {
	height:10vh;
	flex: 0;
	background-color: #ffdddd;
}

.holyGrail {
	height:80vh;
	display: flex;
	flex: 1;
}

.content {
	flex: 1;
	text-align: left;
}

.list {
	display:flex;
	flex-direction: column-reverse;
	flex-grow: 1;
	flex-basis: 0;
	overflow-y: scroll;
	//max-height: 100%;
	//min-height: 100%;
	height: 100%;
	border: solid 1px blue;
}

.listitem{
	border: solid 1px red;
	border-radius: 20px;
	margin:0;
}

.side-nav {
  order: -1;
  width: 200px;
  background-color: #ddffdd;
  display:flex;
  flex-direction: column-reverse;
  //flex-direction: column;
  //align-items:flex-end;
  //align-content:flex-end;
  //border: solid 1px red;
}

.gazo {
  background-color: #eeeeee;
  //align-self:flex-end;
}

$hoge: fuga;
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
