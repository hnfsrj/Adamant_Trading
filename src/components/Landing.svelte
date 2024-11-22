
<script>

    import {getContext, onMount} from 'svelte';

    import {NavStore} from '../store/Store';




    const observeElements = getContext('observeElements');
    const unobserveElements = getContext('unobserveElements');


    

    onMount(()=>{
        let elements = [];

        elements.push(document.querySelector('section>p:first-of-type'));
        elements.push(document.querySelector('section>p:last-of-type'));

        observeElements(elements);

        return () => unobserveElements(elements);
    });

</script>



<div class="blocker">
<section id="landing">
    <p class="effect_blur animate_blur">Electro-Mechanical<br/> LLC</p>

    <p class="effect_blur animate_blur">One stop solution for all<br/>your needs</p>

    
</section>
</div>

<style>
    
    .effect_blur{
        filter: blur(20px);
        transform: scale(2);
    }

    .animate_blur{
        transition: filter 1s, transform 1.5s;
    }



    #landing{
        min-height:100vh;
    }

    section>p:first-of-type{
        margin-top:20%;
        text-align:start;
        font-size:4rem;
        font-weight:700;
        color:var(--red);
        
    }

    section>p:last-of-type{
        color:var(--metal);
        font-size:1.6rem;
        text-align:start;
        margin-top:10%;
        font-weight:500;
    }



@media (min-width:401px){

    section>p:first-of-type{
        font-size:5.5rem;
    }

    section>p:last-of-type{
        font-size:2rem;
        margin-top:13%;

    }


}


@media (min-width:550px){

    /* #landing p:first-of-type>br{
        display:none;
    } */
    
    section>p:first-of-type{
        font-size:5rem;
        margin-top:15%;
    }
    
    section>p:last-of-type{
        margin-top:8%;
        font-size:2.2rem;
    }

}






@media (min-width:701px){

    section>p:first-of-type{
        font-size:5.5rem;
        margin-top:13%;
    }
    
    section>p:last-of-type{
        font-size:2.5rem;
    }


}





@media (min-width:801px){
    
    section>p:last-of-type{
        margin-top:7%;
    }

}



@media (min-width:901px){

	#landing{
		padding:30px 10%;
	}

    section>p:first-of-type{
        font-size:5.7rem;
    }

    section>p:last-of-type{
        margin-top:5%;
        font-size:2.7rem;

    }


}





@media (min-width:1001px){

    section>p:first-of-type{
        margin-top:8%;
        font-size:7rem;
    }

    section>p:last-of-type{
        margin-top:3.5%;
        font-size:3rem;

    }


}

@media (min-width:1051px){
	/* #landing{
		padding-left:15%;
		padding-right:15%;
	} */
}



</style>