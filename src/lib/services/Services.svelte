<script>
    import SectionTitle from "../SectionTitle.svelte"
    import Card from "../Card.svelte"
    import heater_service from "../../assets/heater_service.svg"
    import residential_service from "../../assets/residential_service.svg"
    import construction_service from "../../assets/construction_service.svg"
    import cube_red_blue from "./cube_red_blue.svg"
    import cube_red from "./cube_red.svg"

    export let id = ""

    let title = {
        section:"Our Services",
        slogan:"Reliable Professional Affordable",
        id
    }


    ///     aditinal heater services

    //      In addition to installations and repairs, 
    //      we offer home winterization services to protect 
    //      your plumbing from harsh weather conditions. 
    //      From clogged drains to frozen pipes 
    //      and fireplace maintenance, we provide 
    //      reliable solutions to keep your home safe 
    //      and functional throughout the seasons.

    let cards = 
    [
        {
            image: heater_service,
            header: "Water Heaters",
            text: `We provide installation of <span>boilers, water heaters, and furnaces,</span> 
            ensuring your home stays warm and comfortable year-round. 
            We are also handle <span>repairs for fireplaces and freeze breaks,</span>
            keeping your heating systems running efficiently when you need them most`,
            // text:`Installation Boilers, Water heaters and Furnaces. 
            //     Repair fireplaces, freeze breaks. 
            //     Winterize homes, clogged drains, freeze breaks, & fireplace`,
            class: "blue",
            link: "Schedule now"
            
        },
        {
            image: residential_service,
            header: "Residential Plumbing",
            text: `We inspect and <span>repair leaks, 
            clear clogged drains,</span> and resolve other common 
            plumbing issues to keep your home's plumbing running smoothly. 
            We also <span>install and replace pipes, 
            fixtures, and appliances,</span> ensuring everything 
            functions safely and efficiently for years to come`,
            link: "Schedule now"
            // text:`Inspection and RepairLeaks, clogged drains and other plumbing issue.
            //     Install pipes, fixtures and appliances.`,
        },
        {
            image: construction_service,
            header: "New Construction",
            // text:`Install water supply lines, sewage system, gas lines, and drainage system. 
            //     Follow blue prints and building plans to ensure proper installation. `,
            text: `We install <span>water supply lines, 
            sewage systems, gas lines, and drainage systems,</span>
            ensuring a strong 
            foundation for new construction. 
            We carefully follow blueprints and building 
            plans to guarantee <span>proper installation,</span> 
            meeting all safety and efficiency standards 
            from the ground up`,
            class: "blue",
            link: "Schedule now"


        },
    ]
</script>

<section class="services-container observer-class">
    <SectionTitle props={title}/>
    <div class="card-container">
        {#each cards as c}
            <Card props={c}/>
        {/each}
    </div>
    <img src={cube_red_blue} class="cube blue_red" alt="cube"/>
    <img src={cube_red} class="cube red" alt="cube"/>
</section>

<style>
    .card-container{
        gap: calc(var(--gap-xbig) * 2);
        padding: calc(var(--gap-xbig) * 2) calc(var(--gap-xbig) * 5);
        padding-bottom: calc(var(--gap-xbig) * 12);
        background: linear-gradient(0deg, rgba(255, 255, 255, 0) 0%, rgba(219, 235, 245, 0.5) 70%, #DAEAF5 90%, #DAEAF5 100%);
        box-shadow: 0 -1.25rem 1.25rem #DAEAF5;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(18.75rem, 1fr)); /* Adjust width dynamically */
        align-items: stretch;
        place-items: center;
    }

    
    .services-container{
        position: relative;
        width: 100%;
    }

    .blue_red{
        top: 76%;
        right: 0%;

    }

    .red{
        top: 82%;
        left: -2%;
    }

    @media( width <= 26.875rem ){
        .card-container{
            padding: calc(var(--gap-xbig) * 2);
        }

        .blue_red{
            top: 2%;
            right: 0%;
            width: 30%;
        }

        .red{
            top: 98%;
            left: -2%;
            width: 25%;
        }
    }
</style>