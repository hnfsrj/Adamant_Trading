
<script>

    import {getContext, onMount} from 'svelte';

    import {NavStore} from '../store/Store';

    import Scroller from './Scroller.svelte';



    const observeElements = getContext('observeElements');
    const unobserveElements = getContext('unobserveElements');


    

    onMount(()=>{
        let elements = [];

        elements.push(document.querySelector('section>div>p:first-of-type'));
        elements.push(document.querySelector('section>div>p:nth-of-type(2)'));
        elements.push(document.querySelector('section>div>p:last-of-type'));

        observeElements(elements);

        return () => unobserveElements(elements);
    });

</script>



<div class="blocker">
<section id="landing">

    <div>
        <p class="effect_blur animate_blur">Adamant Trading</p>

        <p class="effect_blur animate_blur">Where trade meets trust</p>

        <p class="effect_blur animate_blur landing_about">Importing, exporting, and distributing goods across various industries, leveraging Dubai’s status as a global trade hub.</p>
    </div>

    <Scroller />

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

    section>div>p:first-of-type{
        margin-top:20%;
        text-align:center;
        font-size:4.5rem;
        font-weight:700;
        color:var(--red);
        
    }

    section>div>p:nth-of-type(2){
        color:var(--metal);
        font-size:2rem;
        text-align:center;
        margin-top:10%;
        font-weight:500;
    }
    
    section>div>p:last-of-type{
        color:black;
        font-size:1.7rem;
        text-align:center;
        margin-top:20%;
        font-weight:400;
    }



@media (min-width:401px){

    section>div>p:first-of-type{
        font-size:6rem;
    }

    section>div>p:nth-of-type(2){
        font-size:2.5rem;
        margin-top:13%;

    }


    section>div>p:last-of-type{
        font-size:1.9rem;
        /* margin-top:20%; */
    }



}


@media (min-width:601px){
    section>div>p:last-of-type{
        /* font-size:1.9rem; */
        margin-top:17%;
    }
}


@media (min-width:550px){

    /* #landing p:first-of-type>br{
        display:none;
    } */
    
    section>div>p:first-of-type{
        font-size:5rem;
        margin-top:15%;
    }
    
    section>div>p:nth-of-type(2){
        margin-top:8%;
        font-size:2.2rem;
    }

}






@media (min-width:701px){

    section>div>p:first-of-type{
        font-size:5.5rem;
        margin-top:10%;
    }
    
    section>div>p:nth-of-type(2){
        font-size:2.5rem;
    }
    
    section>div>p:last-of-type{
        margin-top:80px;
    }


}





/* @media (min-width:801px){

    #landing{
        display: flex;
        justify-content: space-between;
        align-items: start;
    }

    #landing>div{
        width:60%;
    }
    
    section>div>p:nth-of-type(2){
        margin-top:7%;
    }

    section>div>p:first-of-type{
        text-align:start; 
    }

    section>div>p:nth-of-type(2){
        text-align:start;
    }

    section>div>p:last-of-type{
        text-align:start;
    }



} */



@media (min-width:901px){

	#landing{
		padding:30px 10%;
	}

    section>div>p:first-of-type{
        font-size:5.7rem;
    }

    section>div>p:nth-of-type(2){
        margin-top:5%;
        font-size:2.7rem;

    }

    section>div>p:last-of-type{
        width:65%;
        margin:0 auto;
        margin-top:80px;
    }


}





@media (min-width:1001px){

    section>div>p:first-of-type{
        margin-top:8%;
        font-size:7rem;
    }

    section>div>p:nth-of-type(2){
        margin-top:3.5%;
        font-size:3rem;

    }


}



</style>