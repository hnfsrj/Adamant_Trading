

<script>

    export let images = [];
</script>


    <div class="pics_container">

        

        {#each images as image}
            <div class="pic">
                <div style="background-image:url({image.address});" class="image"></div>
                <p class = "img_title">{image.title}</p>
            </div>
        {/each}

    </div>



<style>

    .pics_container{
        width:100%;
        display:flex;
        flex-wrap:wrap;
        justify-content: center;
        align-items: center;
        gap:50px;
        margin-top:80px;
    }

        .pic{
            width:100%;
        }


            .image{
                width:100%;
                aspect-ratio: 16/9;
                background:silver;
                background-size: cover;
                background-repeat: no-repeat;
                background-position: center center;

            }

            .img_title{
                font-weight:500;
                font-size:1.8rem;
                color:black;
                margin-top: 15px;
                text-align: center;
            }




@media (min-width:551px){

    .pic{
        width:80%;
    }

}

@media (min-width:701px){

    .pic{
        width:40%;
    }

}

@media (min-width:1001px){

    .pic{
        width:30%;
    }

}


</style>