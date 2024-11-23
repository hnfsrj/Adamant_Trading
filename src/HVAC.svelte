
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "HVAC",
            "address": "./images/hvac/hvac1.webp",
        },
        {
            "title": "HVAC2",
            "address": "./images/hvac/hvac2.webp",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="HVAC" />
    <Description descript="Reliable heating and cooling systems that perform in tough conditions. " />
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