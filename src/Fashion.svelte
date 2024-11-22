
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [
        {
            "title": "Fashion Kids",
            "address": "./images/fashion/fashion1.jpg",
        },
        {
            "title": "Fashion Men",
            "address": "./images/fashion/fashion2.jpg",
        },
        {
            "title": "Fashion Women",
            "address": "./images/fashion/fashion3.jpg",
        },
    ];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Fashion" />
    <Description descript="Comfortable, stylish clothing for kids, women, and men—perfect for everyday use. " />
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