<script>

    import { getContext, onMount, onDestroy } from "svelte";

    import {NavStore} from '../store/Store';


    $: fix = $NavStore.fix;
    $: wide = $NavStore.wide;
    $: drop = $NavStore.drop;
    $: services = $NavStore.services;


    function nav_buttons(e){

        let target = e.target;


        if (target == document.querySelector('.menu')){
            NavStore.update(current_state => {
                return {...current_state, "drop":true};
            });
            
        }else if (target == document.querySelector('.close')){
            NavStore.update(current_state => {
                return {...current_state, "drop":false, "services":false};
            });
        }else if (target == document.querySelector('.name')){
            document.querySelector('#landing').scrollIntoView({ behavior: 'smooth'});
        }else if (target.matches('.bottom>div.bottom_services') || target.matches('.bottom>div.bottom_services>p')){
            NavStore.update(current_state => {
                if (!services){
                    return {...current_state, "services":true};

                }else{
                    return {...current_state, "services":false};

                }
            });
        }else{
            
            NavStore.update(current_state => {
                return {...current_state, "drop":false, "services":false};
            });
            
        }

    }


    function handle_scrolling(){
        let fix = window.scrollY > document.querySelector('#landing').clientHeight;
        
        if (fix){
            NavStore.update(current_state => {
                return {...current_state, "fix":true};
            });
        }else{
            NavStore.update(current_state => {
                return {...current_state, "fix":false};
            });
        }
    
    }


    function navigation_function(e){
        const target = e.target;

        if (target.matches('.bottom>p') && !(target.matches('.bottom>div.bottom_services') || target.matches('.bottom>div.bottom_services>p'))){
            
            const to = target.innerText.toLowerCase();

            if (to == "home"){
                document.querySelector(`#landing`).scrollIntoView({ behavior: 'smooth'});

            }else{
                document.querySelector(`#${to}`).scrollIntoView({ behavior: 'smooth'});

            }
        }else{
            if (services && !(target.matches('.bottom>div.bottom_services') || target.matches('.bottom>div.bottom_services>p'))){
                NavStore.update(current_state => {
                    return {...current_state, "services":false};
                });
            }
        }

    }


    const nav_observer = getContext('nav_observer');

    let observeding;

    onMount(()=>{
        
        observeding = document.querySelector('nav');

        nav_observer.observe(observeding);
        

        const top = document.querySelector('nav');

        top.addEventListener('click',(e)=>{
            nav_buttons(e);
        });

        handle_scrolling();

        window.addEventListener("scroll", handle_scrolling);

        document.addEventListener("click",(e)=>{
            navigation_function(e);
        })

    });


    onDestroy(()=>{
        top.removeEventListener('click',(e)=>{
            nav_buttons(e);
        })
        
        window.removeEventListener("scroll", handle_scrolling);

        document.removeEventListener('click',(e)=>{
            navigation_function(e);
        })

        nav_observer.unobserve(observeding);
    });

</script>




<nav class:fixation={fix} class:wide={wide} class:scrolled_wide={fix && wide} class="effect_down animate_down">

    <div class="top">

        {#if fix}
            <p class="name">Adamant Trading</p>
        {:else}
            <div class="logo img"></div>
        {/if}

        {#if !wide}
            {#if drop}
                <div class="close img"></div>
            {:else}
                <div class="menu img"></div>
            {/if}
        {/if}

    </div>

    {#if drop || wide}

        {#if wide || !services}
            <div class="bottom">
                
                <p>Home</p>
                <div style="position:relative;" class="bottom_services">

                    <p>Services</p>

                    {#if services && wide}

                        <div style="position:absolute;transform: translateX(-40%);width:250px;" class="dropdown">
                            <a href="/aluminium"><p>Alumunium</p></a>
                            <a href="/steel"><p>Steel</p></a>
                            <a href="/fashion"><p>Fashion</p></a>
                            <a href="/electronics"><p>Electronics</p></a>
                            <a href="/ceramics"><p>Ceramics</p></a>
                            <a href="/finishing"><p>Finishing Materials</p></a>
                            <a href="/hvac"><p>HVAC</p></a>
                            <a href="/construction"><p>Construction Accessories</p></a>
                            <a href="/fmcg"><p>FMCG</p></a>
                        </div>
            
                    {/if}

                </div>
                <p>Contact</p>
                
            </div>
        {/if}

        {#if services && !wide}

            <div class="dropdown">
                <a href="/aluminium"><p>Alumunium</p></a>
                <a href="/steel"><p>Steel</p></a>
                <a href="/fashion"><p>Fashion</p></a>
                <a href="/electronics"><p>Electronics</p></a>
                <a href="/ceramics"><p>Ceramics</p></a>
                <a href="/finishing"><p>Finishing Materials</p></a>
                <a href="/hvac"><p>HVAC</p></a>
                <a href="/construction"><p>Construction Accessories</p></a>
                <a href="/fmcg"><p>FMCG</p></a>
            </div>

        {/if}

    {/if}


</nav>


<style>

    .effect_down{
        transform: translate(0px, -50px);
    }

    .animate_down{
        transition: transform 1.5s;
    }

    nav{
        position:fixed;
        top:0px;
        left:0px;
        width:100%;
        box-sizing: border-box;
        background:var(--translucent_lime);
        backdrop-filter: blur(5px);
        z-index:2;
    }

    
    nav.wide{
        display:flex;
        justify-content: space-between;
        align-items: center;
    }  

        nav.wide .bottom{
            display:flex;
            flex-direction: row;
            flex-wrap:nowrap;
            justify-content: space-between;
            align-items: center;
            background: none;
            box-shadow: none;
            backdrop-filter:blur(0px);
            padding:0px;
            gap:0px;
        }

        nav.wide .bottom p{
            font-weight:500;
            font-size:1.4rem;
            color:var(--metal);
        }

            nav.wide .bottom p:hover{
                color:white;
            }
            
            nav.wide.fixation .bottom p:hover{
                color:white;
                background:var(--red);
            }


            nav.scrolled_wide{
                background:var(--metal);
            }

                nav.scrolled_wide .bottom p{
                    color:white;
                }
                
                nav.scrolled_wide .bottom .bottom_services .dropdown p{
                    color:var(--metal);
                }
                
                nav.scrolled_wide .bottom .bottom_services .dropdown p:hover{
                    color:white;
                }
                

    nav.fixation{
        box-shadow: 0px 4px 7px 2px rgba(0,0,0,0.4);
    }

        nav.fixation .top{
            /* background:none; */
            background:var(--metal);
        }

            nav.fixation .name{
                color:white;
            }

        nav.fixation .top .menu{
            background-image:url("images/menu2.svg");
        }

        nav.fixation .top .close{
            background-image:url("images/close2.svg");
        }

    
        .top{
            display:flex;
            justify-content: space-between;
            align-items: center;
            padding:10px 16px;
        }

            .logo{
                width:80px;
                aspect-ratio: 873/403;
                background-image:url("./images/logo.png");
            }

            .name{
                color:var(--metal);
                font-size:2rem;
                font-weight:700;
            }

                .name:hover{
                    cursor:pointer;
                }



            .menu{
                width:25px;
                aspect-ratio: 1/1;
                background-image:url("images/menu1.svg");
            }

            .close{
                width:25px;
                aspect-ratio: 1/1;
                background-image:url("images/close1.svg");
            }

        .bottom{
            display:flex;
            flex-wrap:wrap;
            flex-direction:column;
            gap:0px;
            padding:15px 16px;
            background:rgba(255,255,255,0.75);
            backdrop-filter: blur(5px);
            box-shadow: 0px 4px 9.5px 0px rgba(0,0,0,0.25);
        }


            .bottom p{
                font-size:1.6rem;
                padding:10px;
                border-radius:10px;
                color:var(--metal);
            }

            .bottom p:hover{
                cursor:pointer;
                background:var(--red);
                color:white;
            }
        
        .dropdown{
            display:flex;
            flex-wrap:wrap;
            flex-direction:column;
            gap:0px;
            padding:15px 16px;
            background:rgba(255,255,255,0.75);
            backdrop-filter: blur(5px);
            box-shadow: 0px 4px 9.5px 0px rgba(0,0,0,0.25);
        }

            .dropdown p{
                font-size:1.6rem;
                padding:10px;
                border-radius:10px;
            }

            .dropdown p:hover{
                cursor:pointer;
                background:var(--red);
                color:white;
            }

        
        a{
            width:100%;
            text-decoration: none;
            color:inherit;
        }
        






@media (min-width:401px){

    nav.fixation .top{
        padding-top:12px;
        padding-bottom:12px;
    }

    .name{
        font-size:2.3rem;
    }

    .logo{
        width:100px;
    }

    .menu{
        width:30px;
    }

}


            
@media (min-width:601px){

    .top{
        padding-left:5%;
        padding-right:5%;
    }



}








@media (min-width:771px){

    .top{
        padding:0px;
    }

    nav.wide{
        padding:15px 3.5%;
    }

    nav.wide>div.bottom{
        /* position:absolute;
        top:52%;
        left:50%;
        transform:translate(-50%,-50%); */
    }

    nav.wide>div.bottom p{
        font-size:1.6rem;
        font-weight:500;
    }


    nav.scrolled_wide{
        padding:5px 3.5%;
    }


}






@media (min-width:801px){
    nav.wide{

        padding:15px 5%;
    }

    nav.scrolled_wide{
        padding:5px 3.5%;
    }
    
    .logo{
        width:120px;
    }

}



</style>








