<template>
	<div id="app" class="app-container">
		<link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">
		<app-header :name="nama"/>
		<div class="content-container">
			<app-question :data="question"/>
       		<app-status/>
		</div>
	</div>
</template>

<script>
	import Header from './components/Header.vue';
	import Question from './components/Question.vue'
	import Status from './components/Status.vue'

	export default {
		name: 'App',
		data() {
			return {
				nama : "Reyvan Rizky",
				question : [{
					question : "this is sample question",
					instruction : "select one of below",
					ansA: "this is sample Ans",
					ansB: "this is sample Ans",
					ansC: "this is sample Ans",
					ansD: "this is sample Ans",
					ansE: "this is sample Ans",
					topic :"this is sample topic",
					ans : "A",
				},{
					question : "this is sample question 2",
					instruction : "select one of below 2",
					ansA: "this is sample Ans 2",
					ansB: "this is sample Ans 2",
					ansC: "this is sample Ans 2",
					ansD: "this is sample Ans 2",
					ansE: "this is sample Ans 2",
					topic :"this is sample topic 2",
					ans : "C",
				}],

			}
		},
		components: {
			appHeader : Header,
			appQuestion : Question,
            appStatus : Status,
		},
	}
</script>

<style>
	*{
		box-sizing: border-box;
		padding: 0;
		margin: 0;
	}
	:root {
		--background-main-color : #edf5e1;
		--primary-color : #a8d0e6 ;
	}
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		display: grid;
		grid-template-rows: 10% 90%;
	}
	.content-container {
        width: 80vw;
        height: 90vh;
        display: grid;
        grid-template-columns: 70% 30%;
        margin: auto;
        padding: 2%;
    }
</style>
