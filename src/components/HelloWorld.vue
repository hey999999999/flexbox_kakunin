<template>
	<div class="hello">
		<header>
			<button @click="onClick">押して</button>
			<h1>header</h1>
		</header>
		<div class="holyGrail">
			<main class="content">
				<div class="list" ref="list">
					<h1 v-for="x in arr" class="listitem">
						{{x}}
					</h1>
				</div>
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
	name: 'HelloWorld',
	data () {
		return {
			arr:[],
			msg: 'Welcome to Your Vue.js App'
		}
	},
	methods:{
		onClick: function(e){
			this.arr.unshift(new Date());
			Vue.nextTick(() => window.scrollTo(this.$refs.list.scrollHeight,0));
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
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
