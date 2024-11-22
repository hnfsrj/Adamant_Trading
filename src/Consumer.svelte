
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = [1,1,1,1,1];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Consumer Goods" />
    <Description descript="Discover a wide range of consumer goods, from cutting-edge electronics to trendy fashion and FMCG products. We bring you trusted brands and high-quality products that cater to diverse preferences and lifestyles." />
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