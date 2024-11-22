

<script>

    import { getContext, onMount } from "svelte";

    const observeElements = getContext('observeElements');
    const unobserveElements = getContext('unobserveElements');


    onMount(()=>{
        let elements = [...document.querySelectorAll('.service_content')];

        observeElements(elements);

        return () => unobserveElements(elements);
    });

</script>

<div class="blocker">
<section id="services">

    <p>Services</p>

    <div class="service_container">
        
        <a href="/#/raw">
            <div class="effect_shrink animate_shrink service_content">

                <div style="background-image:url('./images/air/air1.jpg');" class="service_pic img"></div>

                <p>Raw Materials</p>

            </div>
        </a>

        <a href="/#/consumer">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/pump/pump1.jpg');" class="service_pic img"></div>

            <p>Consumer Goods</p>

        </div>
        </a>

        <a href="/#/specialized">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/lift/lift1.webp');" class="service_pic img"></div>

            <p>Specialized Products</p>
 
        </div>
        </a>

        <a href="/#/construction">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/solar/solar1.jpg');" class="service_pic img"></div>

            <p>Construction Materials</p>

        </div>
        </a>
        
        <a href="/#/comprehensive">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/power/power1.jpg');" class="service_pic img"></div>

            <p>Comprehensive Project Solutions</p>
                
        </div>
        </a>

        <a href="/#/air">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/handling/handling1.jpg');" class="service_pic img"></div>

            <p>Air and Sea Cargo Services</p>
            
        </div>
        </a>

        <a href="/#/sourcing">
        <div class="effect_shrink animate_shrink service_content">

            <div style="background-image:url('./images/industrial/industrial1.jpg');" class="service_pic img"></div>

            <p>Sourcing and Supply Chain</p>
            
        </div>
        </a>


    </div>
    
    
</section>
</div>

<style>

    .effect_shrink{
        transform: scale(0.1);
    }

    .animate_shrink{
        transition: transform 0.5s;
    }


    #services{
        padding-top:80px;
        padding-bottom:80px;
    }

        #services > p{
            text-align:center;
            font-size:3rem;
            font-weight:700;
            color:var(--red);
            margin-bottom:40px;
        }

        .service_container{
            width:100%;
            display:flex;
            flex-wrap:wrap;
            flex-direction:column;
            justify-content: center;
            align-items: center;
            gap:25px;
        }

        a{
            width:100%;
            text-decoration: none;
            color:inherit;
        }

        .service_content{
            box-sizing: border-box;
            width:100%;
        }

            .service_pic{
                width:100%;
                aspect-ratio: 16/9;
                background-color:silver;
                margin-bottom:10px;
                background-size: 100%;
            }


            .service_content > p{
                color:var(--blue_green);
                text-align:center;
                font-size:1.7rem;
                font-weight:600;
                margin-bottom:15px;
            }







@media (min-width:401px){

    #services{
        /* padding: 0px 16px; */
        padding-right:16px;
        padding-left:16px;
        padding-top:100px;
        padding-bottom:100px;

    }

    #services > p{
        font-size:3.2rem;
        margin-bottom:70px;
    }

    .service_container{
        box-sizing: border-box;
        padding:0px 10px;
        gap:30px;
    }


    .service_content > p{
        font-size:2.3rem;
        margin-bottom:20px;
    }

}


@media (min-width:551px){

    a{
        width:80%;
    }


}


@media (min-width:601px){

    #services{
        padding-top:120px;
        padding-bottom:120px;
    }

    .service_container{
        flex-direction:row;
        flex-wrap:wrap;
    }


}


@media (min-width:701px){

    .service_content > p{
        font-size:2rem;
        margin-bottom:20px;
    }

    a{
        width:40%;
    }
    
}


@media (min-width:1001px){

    a{
        width:30%;
    }

}


</style>