<script>
    import Button from "../bottons/button.svelte"
    import massage_ic from "../../assets/message_white.svg"
    import hero_svg from "../../assets/hero_svg.svg"
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
        padding: calc(var(--gap-xbig) * 4) clamp(1.2rem, 6vw, 8rem);
        justify-content: center;
        align-items: center;
        gap: var(--gap-xbig);
        /* min-height, not height: wrapped text must be able to grow the hero
           instead of spilling into the next section. */
        min-height: 82vh;
        position: relative;
        overflow-y: visible;
    }

    .item-1{
        display: flex;
        flex-direction: column;
        gap: var(--gap-xbig);
        flex: 1 1 0;
        height: fit-content;
        max-width: 87.5rem;
        min-width: 0;
    }

    h1{
        max-width: 45.063rem;
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
        /* The illustration is detailed: give it ~60% of the row, not half. */
        flex: 1.5 1 0;
        min-width: 0;
        display: flex;
        justify-content: center;
    }

    .hero-svg{
        width: 100%;
        max-width: 52rem;
        height: auto;
    }

    p{
        max-width: 30rem;
        font-weight: 500;
        letter-spacing: 0.08em;
    }

    .button-wrapper{
        width: 100%;
        max-width: 20rem;
    }

    /* Tablets (incl. 1024-1032px iPads) and phones: illustration on top, text
       underneath, whole hero fits one screen below the logo bar. */
    @media( width <= 66rem ){
        main{
            /* One column width shared by illustration and text, growing with
               the screen: ~670px on iPad Mini, ~790px on iPad Pro 13. */
            --hero-col: min(100%, 30rem + 30vw);
            flex-direction: column-reverse;
            padding: var(--gap-xbig) calc(var(--gap-xbig) * 2) calc(var(--gap-xbig) * 2);
            justify-content: center;
            /* Breathing room between illustration and text, scaled to the
               screen height. */
            gap: clamp(2rem, 5svh, 5rem);
            min-height: calc(100svh - 6rem);
        }

        .item-1{
            width: var(--hero-col);
            max-width: none;
            gap: var(--gap-big);
        }

        h1{
            margin-bottom: 0;
            font-size: clamp(3rem, 2rem + 6.5vw, 6rem);
        }

        p{
            max-width: none;
            font-size: clamp(1rem, 0.6rem + 1.2vw, 1.5rem);
        }

        /* Fills the shared column; the height cap keeps the whole hero on one
           screen on shorter tablets. */
        .hero-svg{
            width: var(--hero-col);
            max-width: 100%;
            max-height: 44svh;
            object-fit: contain;
        }

        /* Block, not flex: lets the image size purely from its height cap and
           ratio instead of being stretched or shrunk as a flex item. */
        .item-2{
            display: block;
            flex: none;
            width: 100%;
            text-align: center;
            padding-top: 0;
        }

        .button-wrapper{
            max-width: none;
        }
    }

    @media( width <= 26.875rem ){
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