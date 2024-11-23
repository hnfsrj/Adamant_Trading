<script>

	import { onMount, onDestroy, setContext } from "svelte";

	import {NavStore} from './store/Store';
	import {OtherStates} from './store/Other';
	import {ServicesState} from './store/Other';
	import {MapState} from './store/Other';

	import Nav from './components/Nav.svelte';
	import Landing from './components/Landing.svelte';
	import Services from './components/Services.svelte';
	import Contact from './components/Contact.svelte';


	const nav_observer = new IntersectionObserver((entries) => {
		entries.forEach(entry => {
			if (entry.isIntersecting) {
				const classes = Array.from(entry.target.classList);

				entry.target.classList.remove(classes[0]);

				observer.unobserve(entry.target);
			}
			
		});
	}, {
		rootMargin: '0px',
		threshold: 0
	});



	const observer = new IntersectionObserver((entries) => {
		entries.forEach(entry => {
			if (entry.isIntersecting) {
				const classes = Array.from(entry.target.classList);

				entry.target.classList.remove(classes[0]);

				observer.unobserve(entry.target);
			}
			
		});
	}, {
		rootMargin: '-20px',
		threshold: 0
	});



	const parent_observer = new IntersectionObserver((entries) => {
		entries.forEach(entry => {
			if (entry.isIntersecting) {

				const elements = Array.from(entry.target.children);

				elements.forEach(element=>{

					const classes = Array.from(element.classList);

					element.classList.remove(classes[0]);

				});

				observer.unobserve(entry.target);
				
			}
			
		});
	}, {
		rootMargin: '-20px',
		threshold: 0
	});



	function observeElements(elements) {
        elements.forEach((element) => {
            observer.observe(element);
        });
    }

    function unobserveElements(elements) {
        elements.forEach((element) => {
            observer.unobserve(element);
        });
    }

	setContext('nav_observer', nav_observer);
	setContext('observer', observer);
	setContext('parent_observer', parent_observer);
	setContext('observeElements', observeElements);
	setContext('unobserveElements', unobserveElements);











	function resize_handler(){
		let width = window.innerWidth;

		ServicesState.update(current_state => {
            return {...current_state};
        });

		if (width >= 771){
			if(!$NavStore.wide){
				NavStore.update(current_state => {
					return {...current_state, "wide":true};
				});

			}
		}else{
			if($NavStore.wide){
				NavStore.update(current_state => {
					return {...current_state, "wide":false};
				});
			}
			
		}

		
		if (width >= 901){
			if(!$MapState.wide){
				MapState.update(current_state => {
					return {...current_state, "wide":true};
				});

			}
		}else{
			if($MapState.wide){
				MapState.update(current_state => {
					return {...current_state, "wide":false};
				});
			}
			
		}


		if (width>=995){
			OtherStates.update(current_state => {
                return {...current_state, "split":true};
            });
		}else{
			OtherStates.update(current_state => {
                return {...current_state, "split":false};
            });
		}

	}

	onMount(()=>{
		resize_handler();
		window.addEventListener("resize", resize_handler);
	});
	
	onDestroy(()=>{
		window.removeEventListener("resize", resize_handler);
	});


</script>





<div id="container">
	<Nav/>
	<Landing/>
	<Services/>
	<Contact/>
</div>


<style>

</style>
