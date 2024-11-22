

<script>

	import Router from 'svelte-spa-router';
	import Home from './Home.svelte';
	import Raw from './Raw.svelte';
	import Consumer from './Consumer.svelte';
	import Specialized from './Specialized.svelte';
	import Construction from './Construction.svelte';
	import Comprehensive from './Comprehensive.svelte';
	import Air from './Air.svelte';
	import Sourcing from './Sourcing.svelte';

	// function resize_handler(){
	// 	let width = window.innerWidth;

	// 	console.log(width);
	// }


	// resize_handler();
	// window.addEventListener("resize", resize_handler);

</script>


<Router routes={{
	'/': Home,
	'/raw': Raw,
	'/consumer': Consumer,
	'/specialized': Specialized,
	'/construction': Construction,
	'/comprehensive': Comprehensive,
	'/air': Air,
	'/sourcing': Sourcing
}} />
