<script>
    export let props
</script>

<section id={props.id}>
    <h3>{props.section}</h3>
    <h2 class="title-bg">{props.slogan}</h2>
</section>


<style>
    h2{
        width: fit-content;
        
    }

    h3{
        font-weight: 900;
        font-size: var(--font-sm);
        letter-spacing: 0.39em;
        padding-bottom: var(--gap-big);
        padding-left: 0.2rem;
    }

    section{
        padding: 0  calc(var(--gap-xbig) * 2.5);
        padding-top: calc(var(--gap-xbig) * 1);
        padding-bottom: calc(var(--gap-big) * 2);


    }
</style>