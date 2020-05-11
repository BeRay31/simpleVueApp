<template>
	<div id="app" class="app-container">
		<link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">
		<app-header :name="nama" class="app-header"/>
		<div class="home-user" v-if=" nama=='' && !submit">
			<app-home @nameChanged="changeNama($event)"/>
		</div>
		<div class="content-container" v-else-if="nama!=''&& !submit">
			<app-question :data="question" :index="index" @indexChanged="changeIndex($event)" />
       		<app-status :data="question" :index="index" @submitted="submit=true"/>
		</div>
		<div class="submit-screen" v-else-if="submit">
			<app-submit :questionKey="ans" :data="question"/>
		</div>
	</div>
</template>

<script>
	import Header from './components/Header.vue';
	import Question from './components/Question.vue';
	import Status from './components/Status.vue';
	import Home from './components/Home.vue';
	import Submit from './components/Submit.vue';
	import { eventBus } from './main.js';

	export default {
		name: 'App',
		data() {
			return {
				nama : '',
				question : [],
				ans : [],
				index : 0,
				submit : false,
			}
		},
		components: {
			appHeader : Header,
			appQuestion : Question,
            appStatus : Status,
			appHome :  Home,
			appSubmit : Submit,
		},
		methods: {
			changeIndex(index) {
				this.index = index;
			},
			changeNama(nama) {
				this.nama = nama;
			},
			submit() {
				this.submit = true;
			}
		},
		created() {
			
			for(let i = 0; i<20;i++) {
				this.question.push({
					question : "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem, unde. Enim rem nostrum laborum porro saepe. Quod deserunt nostrum officia eveniet quis architecto beatae exercitationem dolorum expedita consequuntur illum voluptatem, temporibus similique obcaecati natus in aliquid repellat? Aspernatur ratione necessitatibus, voluptatum facere pariatur ducimus et ipsa vel, vero voluptatibus accusamus soluta earum itaque non neque cupiditate quia eos dolor voluptates iure maiores. Nemo vel numquam quis maxime suscipit laboriosam molestiae cum culpa eligendi consequatur aperiam aliquid fugiat accusantium reprehenderit perspiciatis ut voluptatum possimus mollitia, quas sequi! Nobis modi magni corrupti labore odio ad, tenetur temporibus id quisquam nulla, mollitia reprehenderit!",
					instruction : "sLorem ipsum dolor sit amet, consectetur adipisicing elit. Cum facere quae perspiciatis dolores, commodi voluptates incidunt amet minima, maiores nihil natus asperiores molestiae eaque voluptatum accusamus architecto facilis veniam ut!",
					ansA: "tLorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus error assumenda hic culpa est aperiam odio quisquam quae nobis repudiandae.",
					ansB: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus error assumenda hic culpa est aperiam odio Lorem Ipsume.",
					ansC: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus error assumenda hic culpa est aperiam odio Lorem Ipsume.",
					ansD: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus error assumenda hic culpa est aperiam odio Lorem Ipsume.",
					ansE: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus error assumenda hic culpa est aperiam odio Lorem Ipsume.",
					topic :"Lorem Ipsum",
					ans : '',
				});
			}
			for(let i = 0; i<20;i++) {
				this.ans.push('A');
			}
		}
	}
</script>

<style>
	*{
		box-sizing: border-box;
		padding: 0;
		margin: 0;
		line-height: 1.6rem;
	}
	:root {
		--background-main-color : #edf5e1;
		--primary-color : #a8d0e6 ;
		--secondary-color: #009ACE;
		--hover-color: #aab19f;
		--active-link-color :rgb(72, 185, 223);
		--border-color :rgb(14, 88, 112);
		--secondary-border-color :rgb(35, 56, 114);
		--click-color : #3aace9 ;
	}
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}
	.content-container {
        width: 90vw;
        height: 90vh;
        display: grid;
        grid-template-columns: 65% 35%;
        margin: auto;
        padding: 2%;
    }
	.borderNshadow{
		border: 4px solid var(--border-color);
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
	}
	.app-header {
		padding: 0.6em;
	}
	.use-merriweather {
        font-family: 'Merriweather Sans', sans-serif;
    }
	.use-bree {
		font-family: 'Bree Serif', serif;
	}
	.use-roboto {
		font-family: 'Roboto', sans-serif;
	}
	.use-lato {
		font-family: 'Lato', sans-serif;
	}
	.use-sans-pro {
		font-family: 'Source Sans Pro', sans-serif;
	}
	.use-raleway {
		font-family: 'Raleway', sans-serif;
	}
	.use-open-sans {
		font-family: 'Open Sans', sans-serif;
	}
	.use-bangers {
		font-family: 'Bangers', cursive;
	}
	.use-staat {
		font-family: 'Staatliches', cursive;
	}
</style>
