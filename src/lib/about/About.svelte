<script>
    import SectionTitle from "../SectionTitle.svelte";
    import tools from "../../assets/tools.svg"
    import cube_blue from "./cube_blue.svg"
    import cube_red from "./cube_red.svg"

    export let id = ""

    let title = {
        section:"About",
        slogan:"Why Choose Knockout?",
        id
    }
</script>

<section>
    <SectionTitle props={title}/>
    <div class="about-div observer-class">
        <img src={tools} class="svg" alt="tools"/>
        <p>
            <span>
                With over 27 years of 
                experience in the plumbing industry,
            </span> 
            we bring unmatched expertise to every job. 
            As a family-owned business, 
            we care deeply about our community 
            and strive to offer best plumbing solutions.
        </p>

        <p>
            We take great pride in serving the <span>Estes Park</span>
            area and nearby towns, building strong relationships 
            with the people who make this community special. 
            Our customers aren't just clients—they're our neighbors, 
            friends, and fellow community members. 
            That's why we are committed to providing <span>reliable and honest service with the best prices,</span>
            ensuring that every home and business we work with receives the care and attention it deserves
        </p>

        <p>
            Our goal is to make as <span>easy and comfortable experience</span>
            as possible, so you can feel confident knowing 
            you have a plumbing team that truly cares. 
            When you call us, you're not just getting a plumber—you're 
            getting a trusted neighbor.
        </p>
    </div>
    <img src={cube_blue} class="cube blue" alt="cube"/>
    <img src={cube_red} class="cube red" alt="cube"/>
</section>

<style>
    section{
        /* padding: calc(var(--gap-xbig) * 5) 0; */
        position: relative;
        padding-top: calc(var(--gap-xbig) * 10);
        padding-bottom: calc(var(--gap-xbig) * 5);


    }

    .about-div {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: calc(var(--gap-xbig) * 2);
        padding-top: calc(var(--gap-xbig) * 2);
        background: linear-gradient(0deg, rgba(255, 255, 255, 0) 0%, rgba(219, 235, 245, 0.5) 70%, #DAEAF5 90%, #DAEAF5 100%);
        box-shadow: 0 -1.25rem 1.25rem #DAEAF5;
    }

    .about-div img{
        width: 60%;
    }

    .about-div p{
        font-weight: 900;
        font-size: 1.75rem;
        line-height: var(--linehieght-md);
        letter-spacing: 0.08em;
        color: var(--secondery-fnt-clr);
        width: 65rem;
    }

    .about-div p span{
        color: var(--primary-fnt-clr);
    }

    .blue{
        top: 12%;
        right: 12%;

    }

    .red{
        top: 65%;
        left: 2%;
    }



</style>