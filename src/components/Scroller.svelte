

<script>

    import {onMount} from "svelte";

    let scrollableDiv;

    function left(){
        scrollableDiv.scrollLeft = 0;
    }

    onMount(()=>{

        scrollableDiv = document.querySelector(".scroller_container");

        window.addEventListener("load", left);

        window.addEventListener("resize", left);

        return () => {
            window.removeEventListener("load", left)
            window.removeEventListener("resize", left)
        };
    });

</script>


<div class="scroller_container">

    
    
    <div class="scrolled">

        <div class="scroll">

            <div style="background-image:url('./images/aluminium/aluminium2.webp');" class="scroll_pic"></div>

        </div>
        
        <div class="scroll">

            <div style="background-image:url('./images/finishing/finishing2.webp');" class="scroll_pic"></div>

        </div>
        
        <div class="scroll">

            <div style="background-image:url('./images/ceramics/ceramics2.webp');" class="scroll_pic"></div>

        </div>

        <div class="scroll">

            <div style="background-image:url('./images/construction/construction2.webp');" class="scroll_pic"></div>

        </div>


        <div class="scroll">

            <div style="background-image:url('./images/hvac/hvac2.webp');" class="scroll_pic"></div>

        </div>
        
        
        
        <div class="scroll">

            <div style="background-image:url('./images/steel/steel2.webp');" class="scroll_pic"></div>

        </div>
        
        
        <div class="scroll">

            <div style="background-image:url('./images/finishing/finishing3.webp');" class="scroll_pic"></div>

        </div>



        <div class="scroll">

            <div style="background-image:url('./images/electronics/electronics2.webp');" class="scroll_pic"></div>

        </div>





    </div>
    
    <div class="scrolled">

        <div class="scroll">

            <div style="background-image:url('./images/aluminium/aluminium2.webp');" class="scroll_pic"></div>

        </div>
        
        <div class="scroll">

            <div style="background-image:url('./images/finishing/finishing2.webp');" class="scroll_pic"></div>

        </div>
        
        <div class="scroll">

            <div style="background-image:url('./images/ceramics/ceramics2.webp');" class="scroll_pic"></div>

        </div>

        <div class="scroll">

            <div style="background-image:url('./images/construction/construction2.webp');" class="scroll_pic"></div>

        </div>


        <div class="scroll">

            <div style="background-image:url('./images/hvac/hvac2.webp');" class="scroll_pic"></div>

        </div>
        
        
        
        <div class="scroll">

            <div style="background-image:url('./images/steel/steel2.webp');" class="scroll_pic"></div>

        </div>
        
        
        <div class="scroll">

            <div style="background-image:url('./images/finishing/finishing3.webp');" class="scroll_pic"></div>

        </div>


        <div class="scroll">

            <div style="background-image:url('./images/electronics/electronics2.webp');" class="scroll_pic"></div>

        </div>





    </div>
    
    
    


</div>



<style>


    .scroller_container{
        overflow:hidden;
        display:flex;
        justify-content: start;
        flex-wrap:nowrap;
        box-sizing: border-box;
        margin-top:30%;
    }


    .scrolled{
        display:flex;
        flex-wrap:nowrap;
        align-items:start;
        justify-content: start;
        width:fit-content;
        animation: 25s slide infinite linear;
        padding-bottom:3px;
        /* overflow: visible; */
    }

    @keyframes slide{
        from{
            transform:translateX(0);
        }

        to{
            transform:translateX(-100%);
        }
    }

        .scroll{
            display:flex;
            flex-direction: column;
            justify-content: start;
            align-items: center;
            margin:0px 10px;
            /* overflow: visible; */
        }


            .scroll_pic{
                background:silver;
                width:130px;
                aspect-ratio: 1/1;
                background-size: cover;
                background-repeat: no-repeat;
                background-position: center center;
                border:2px solid var(--metal);
                box-shadow: -2px 2px 4px 1px var(--metal);
            }


@media (min-width:401px){

    /* .scroller_container{
        margin-top:30%;
    } */

    /* .scroll{
        margin:0px 10px;
    } */


    .scroll_pic{
        width:150px;
    }

}

@media (min-width:601px){
    .scroller_container{
        margin-top:25%;
    }
}



@media (min-width:701px){
    .scroll_pic{
        width:200px;
    }

    .scroller_container{
        margin-top:80px;
    }

}

/* 
@media (min-width:801px){

    .scroller_container{
        flex-direction: column;
    }

    .scrolled{
        flex-direction: column;
    }

    .scroll{
        margin:10px 0px;
    }

} */



</style>