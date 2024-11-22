
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Paints",
            "address": "./images/finishing/finishing1.jpeg",
        },
        {
            "title": "Sealants",
            "address": "./images/finishing/finishing2.jpeg",
        },
        {
            "title": "Varnishes",
            "address": "./images/finishing/finishing3.jpeg",
        },
        {
            "title": "Wallpapers",
            "address": "./images/finishing/finishing4.jpeg",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Finishing Materials" />
    <Description descript="Essential materials like paints, sealants, and wallpapers to complete your projects with style. " />
    <Pictures images = {imgs} />
</div>


<style>

    #container{
        width:100vw;
        box-sizing: border-box;
        min-width:300px;
        max-width:1300px;
        margin:0 auto;
        padding:70px 5%;
    }


@media (min-width:601px){
    #container{
        padding:100px 5%;
    }


}



</style>