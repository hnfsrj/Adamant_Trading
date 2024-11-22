
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Aluminium Flat Busbar",
            "address": "./images/aluminium/aluminium1.jpg",
        },{
            "title": "Aluminium Rectangular Pipe",
            "address": "./images/aluminium/aluminium2.jpg",
        },{
            "title": "Aluminium Square Tube",
            "address": "./images/aluminium/aluminium3.jpg",
        },{
            "title": "Aluminum Window Section",
            "address": "./images/aluminium/aluminium4.jpg",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Alumunium" />
    <Description descript="Strong, lightweight materials suited for any project or purpose." />
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