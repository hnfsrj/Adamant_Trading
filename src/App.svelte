

<script>

	import Router from 'svelte-spa-router';
	import Home from './Home.svelte';
	import Aluminium from './Aluminium.svelte';
	import Steel from './Steel.svelte';
	import Fashion from './Fashion.svelte';
	import Electronics from './Electronics.svelte';
	import Ceramics from './Ceramics.svelte';
	import Finishing from './Finishing.svelte';
	import HVAC from './HVAC.svelte';
	import Construction from './Construction.svelte';
	import FMCG from './FMCG.svelte';

	function resize_handler(){
		let width = window.innerWidth;

		console.log(width);
	}


	resize_handler();
	window.addEventListener("resize", resize_handler);

</script>


<Router routes={{
	'/': Home,
	'/aluminium': Aluminium,
	'/steel': Steel,
	'/fashion': Fashion,
	'/electronics': Electronics,
	'/ceramics': Ceramics,
	'/finishing': Finishing,
	'/hvac': HVAC,
	'/construction': Construction,
	'/fmcg': FMCG
}} />
