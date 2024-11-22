
<script>
    import {onMount} from "svelte";

    let scrollableDiv;

    function toper(){
        scrollableDiv.scrollTop = 0;
    }

    onMount(()=>{

        scrollableDiv = document.querySelector("nav").parentElement;

        window.addEventListener("load", toper);

        return () => {
            window.removeEventListener("load", toper)
        };
    });
</script>

<nav>

    <a href="/#/"><p class="name">MESSP</p></a>

</nav>


<style>

    nav{
        position:fixed;
        top:0px;
        left:0px;
        width:100%;
        box-sizing: border-box;
        background:var(--metal);
        backdrop-filter: blur(5px);
        box-shadow: 0px 4px 7px 2px rgba(0,0,0,0.4);
        padding:10px 16px;
        z-index:2;
    }

    a{
        text-decoration: none;
        color:inherit;
    }

    .name{
        color:White;
        font-size:2rem;
        font-weight:700;
    }





@media (min-width:401px){
    
    nav{
        padding-top:12px;
        padding-bottom:12px;
    }

    .name{
        font-size:2.3rem;
    }

}



@media (min-width:601px){

    nav{
        padding-left:5%;
        padding-right:5%;
    }


}

@media (min-width:771px){

    nav{
        padding:15px 3.5%;
    }


}

@media (min-width:801px){

    nav{
        padding:15px 5%;
    }


}

</style>