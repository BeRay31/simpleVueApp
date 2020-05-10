<template>
	<div id="app" class="app-container">
		<app-header/>
		<div class="content-container">
			<app-question/>
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
		components: {
			appHeader : Header,
			appQuestion : Question,
            appStatus : Status,
		}
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
