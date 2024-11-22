
<script>

    import Top from './components/sub_components/Top.svelte';
    import Back from './components/sub_components/Back.svelte';
    import Title from './components/sub_components/Title.svelte';
    import Description from './components/sub_components/Description.svelte';
    import Pictures from './components/sub_components/Pictures.svelte';

    let imgs = ['./images/comprehensive/comprehensive1.jpeg','./images/comprehensive/comprehensive2.jpeg'];

</script>


<div id="container">
    <Top />
    <Back />
    <Title name="Comprehensive Project Solutions" />
    <Description descript="Simplify your projects with our one-stop solutions for all your needs. From planning to procurement and delivery, we provide seamless and efficient support for projects of any scale." />
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