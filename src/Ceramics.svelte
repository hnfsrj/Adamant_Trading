
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Ceramics Tiles",
            "address": "./images/ceramics/ceramics1.webp",
        },
        {
            "title": "Disabled Wash Basin",
            "address": "./images/ceramics/ceramics2.webp",
        },
        {
            "title": "Washbasin Mixer",
            "address": "./images/ceramics/ceramics3.webp",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Ceramics" />
    <Description descript="High quality tiles and fittings designed to enhance both style and function your space." />
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