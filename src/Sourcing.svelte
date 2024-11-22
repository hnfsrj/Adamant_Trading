
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = ['./images/sourcing/sourcing1.jpg','./images/sourcing/sourcing2.jpg','./images/sourcing/sourcing3.jpg','./images/sourcing/sourcing4.jpg','./images/sourcing/sourcing5.jpg','./images/sourcing/sourcing6.jpg','./images/sourcing/sourcing7.jpg','./images/sourcing/sourcing8.jpg',];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Sourcing and Supply Chain" />
    <Description descript="Leverage our expertise in sourcing agricultural commodities from East Africa and supplying them to markets in the UAE, Middle East, and Asia. Our streamlined supply chain guarantees quality and timely delivery for your business." />
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