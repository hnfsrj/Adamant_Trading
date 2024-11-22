
<script>
    import { getContext, onMount } from "svelte";

    const observer = getContext('observer');

    let observeding;
    onMount(()=>{

        observeding = document.querySelector("form>input[type='submit']")

        observer.observe(observeding);

        return () => observer.unobserve(observeding);
    });
</script>

<div class="form_container">

    <p>Get in Touch</p>

    <form action="" method="POST">

        <input type="text" placeholder="Name" name="Name" required />
        <input type="email" placeholder="Email" name="Email" required />
        <input type="text" placeholder="Subject" name="Subject" required />
        <textarea placeholder="Message" name="Message" required></textarea>

        <input class="effect_wide animate_wide" type="submit" value="Submit" />
    </form>


</div>

<style>

    form>input[type="submit"].effect_wide{
        width:0%;

    }

    .animate_wide{
        transition: width 0.5s;
    }


    .form_container{
        background:white;
        font-family:"itim";
        box-sizing: border-box;
        width:100%;
        border-radius:10px;
        box-shadow: 0px 0px 4px 2px rgba(0,0,0,0.25);
        padding:20px 10px;
        font-size:1.6rem;
        
    }

        .form_container>p{
            margin-bottom:15px;
        }

        form{}

            form input:not([type="submit"]){
                border:2px solid black;
                border-radius:10px;
                width:100%;
                box-sizing: border-box;
                padding:0px 10px;
                height:40px;
                margin-bottom:10px;
            }

            form textarea{
                border:2px solid black;
                border-radius:10px;
                box-sizing: border-box;
                padding:5px 10px;
                width:100%;
                resize: none;
                height:100px;
            }

            form input[type="submit"]{
                display: block;
                color:white;
                background:var(--red);
                outline:none;
                border:none;
                box-shadow: 0px 3px 3px 1px rgba(0,0,0,0.25);
                width:80%;
                margin:0 auto;
                margin-top:30px;
                border-radius:15px;
                height:40px;
                font-size:2rem;
                font-weight:700;
            }





@media (min-width:401px){

    .form_container{
        padding:25px 10px;
        
    }

    .form_container>p{
        margin-bottom:25px;
        font-size:2rem;
    }

    form input:not([type="submit"]){
        height:55px;
        margin-bottom:15px;
        font-size:1.8rem;
    }


    form textarea{
        height:140px;
        padding:10px;
        font-size:1.8rem;
    }


    form input[type="submit"]{
        height:50px;
        font-size:2.5rem;
    }



}


@media (min-width:501px){

    .form_container{
        width:95%;
        margin:0 auto;
        padding:25px 20px;
    }

    form input:not([type="submit"]){
        height:50px;
        margin-bottom:15px;
        font-size:1.8rem;
    }


    form textarea{
        height:140px;
        padding:10px;
        font-size:1.6rem;
    }


    form input[type="submit"]{
        height:50px;
        font-size:2.5rem;
        width:70%
    }


}




@media (min-width:601px){

    .form_container{
        width:87%;
        padding:30px 5%;
    }

}

@media (min-width:751px){

.form_container{
    width:85%;
    padding:30px 5%;
}

}


@media (min-width:801px){
    .form_container{
        width:80%;
    }
}


@media (min-width:851px){
    .form_container{
        width:70%;
    }
}


@media (min-width:901px){
    
    .form_container{
        margin:0px;
        width:50%;
        padding:30px 2%;
    }
}


@media (min-width:1001px){
    
    .form_container{
        width:45%;
        padding:40px 3%;
    }

}




</style>