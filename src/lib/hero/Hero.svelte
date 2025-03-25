<script>
    import Button from "../bottons/button.svelte"
    import massage_ic from "../../assets/message_white.svg"
    import hero_svg from "../../assets/hero.svg"
    import cube_blue from "./cube_blue.svg"
    import cube_red from "./cube_red.svg"

    export let id = ""

</script>

<main id={id}>
    <section class="item-1 home observer-class">
        <h1 class="title-bg">Your Local Plumbing Experts</h1>
        <p>
            From minor leaks to major repairs, we have you covered. 
            As a trusted, family-owned business, we provide reliable and 
            professional plumbing solutions to meet all your need.
        </p>
        <div class="button-wrapper">
            <Button props={{
                icon:massage_ic,
                text:'Get a Free Estimate',
                width: "100%",
                onClick: () => {
                            const section = document.getElementById("contacts")
                            if (section) {
                                section.scrollIntoView({ behavior: 'smooth' })
                            }
                        }
                }}/>
        </div>
    </section>
    <section class="item-2">
        <img src={hero_svg} class="hero-svg" alt="hero-svg"/>
    </section>
    <img src={cube_blue} class="cube blue" alt="cube"/>
    <img src={cube_red} class="cube red" alt="cube"/>
</main>

<style>
    main{
        display: flex;
        padding:  calc(var(--gap-xbig) * 4);
        justify-content: center;
        align-items: center;
        align-items: top;
        height: 82vh;
        position: relative;
        overflow-y: visible;
    }

    .item-1{
        display: flex;
        flex-direction: column;
        gap: var(--gap-xbig);
        flex: 1;
        height: fit-content;
        max-width: 87.5rem;
    }

    h1{
        width: 45.063rem;
        margin-bottom: calc(var(--gap-xbig));
    }

    .blue{
        top: 45%;
        left: -1%;
    }

    .red{
        top: 80%;
        right: 0%;
    }

    .item-2{
        padding-top: calc(var(--gap-xbig) * 2);
    }

    p{
        width: 30rem;
        font-weight: 500;
        letter-spacing: 0.08em;
    }

    .button-wrapper{
        width: 20rem;
    }

    
    @media( width <= 26.875rem ){
        main{
            flex-direction: column-reverse;
            padding:  calc(var(--gap-xbig) * 2);
            justify-content: space-between;
            gap: var(--gap-xbig);
            height: 90vh;
        }

        .hero-svg{
            width: 24.875rem ;
        }

        h1{
            margin-top: auto;
            margin-bottom: auto;
            width: 22rem;
        }


        .item-2{
            padding-top: var(--gap-md);
        }

        p{
            width: 22rem;
        }

        .button-wrapper{
            width: 100%;

        }

        .blue{
            top: 72%;
            left: -1%;
            width: 30%;
        }

        .red{
            top: 92%;
            right: 0%;
            width: 22%;
        }

    }

</style>