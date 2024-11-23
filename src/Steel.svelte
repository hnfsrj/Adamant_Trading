
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Cold Rolled Steel Sheets:Coils",
            "address": "../images/steel/steel1.jpg",
        },{
            "title": "Hot Rolled Steel",
            "address": "../images/steel/steel2.jpg",
        },{
            "title": "Reinforcement Steel Bars",
            "address": "../images/steel/steel3.jpg",
        },{
            "title": "Steel Billets",
            "address": "../images/steel/steel4.jpg",
        },{
            "title": "Wire Rods",
            "address": "../images/steel/steel5.jpg",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Steel" />
    <Description descript="Durable steel options ideal for construction, manufacturing, and beyond." />
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