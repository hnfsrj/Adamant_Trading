
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Desktop Computer",
            "address": "./images/electronics/electronics1.jpg",
        },
        {
            "title": "Security Cameras",
            "address": "./images/electronics/electronics2.jpg",
        },
        {
            "title": "Vacuum Cleaner",
            "address": "./images/electronics/electronics3.jpg",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Electronics" />
    <Description descript="Smart tools and gadgets that make work and home life easier and more efficient. " />
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