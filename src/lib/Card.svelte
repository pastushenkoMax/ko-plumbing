<script>
    import NavButton from "./bottons/navButton.svelte";
    export let props

</script>

<div class="card {props.class}">
    <img src={props.image} alt="card_img">
    <section>
        <h3>
            {props.header}
        </h3>
        <p>
            {@html props.text}
        </p>
        <NavButton props={{
            onClick:(id)=>{
                const section = document.getElementById(id);
                if (section) {
                    section.scrollIntoView({ behavior: 'smooth' });
                }
            },
            id:"contacts",
            text: props.link,
            class: "link"
        }}/>
    </section>
</div>

<style>

    .card{
        display: flex;
        padding: var(--gap-big);
        flex-direction: column;
        align-items: center;

        border-radius: var(--border-rad);
        background-color: var(--secondery-clr);
        
        box-shadow: 20px 20px 60px #e8ecf0,
        -2px -2px 40px #eff1f3;
        
        max-width: fit-content;
        gap: var(--gap-xbig);
        
        background: #ffffff;
        background-color: #e2beb2ab;
        background-color: #f0c5b5a2;
        min-height: 100%;
    }
    .blue{
        background-color: var(--accent-clr);
        background: #ffffff;
        background-color: #b4d8f36e;
        background-color: #c7d9eabb;


    }

    .card img{
        /* flex: 1; */
        height: 290px;
        width: 320px;
    }

    section{
        flex: 1;
        /* padding-top: var(--gap-big); */
        display: flex;
        flex-direction: column;
        gap: var(--gap-big);
    }

    section h3{
        /* padding-bottom: var(--gap-big); */
        /* text-align: center; */
        font-weight: 900;
        font-size: 1.6rem;
        letter-spacing: 0.08em;
    }

    section p {
        margin-top: auto;
        margin-bottom: auto;
        max-width: 50ch;
        font-weight: 900;
        letter-spacing: 0.08em;
        color: var(--secondery-fnt-clr);
    }

    .card :global(section p span){
        color: var(--primary-fnt-clr);
    }





</style>