
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = ['./images/raw/raw1.jpg','./images/raw/raw2.jpg','./images/raw/raw3.jpg','./images/raw/raw4.jpg'];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Raw Materials" />
    <Description descript="Empower your industry with premium raw materials like steel, aluminum, and other essential inputs. Sourced from trusted suppliers, our materials ensure unmatched quality and reliability for your manufacturing and industrial needs." />
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