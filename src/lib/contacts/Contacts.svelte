<script>
    import SectionTitle from "../SectionTitle.svelte"
    import cube_blue from "./cube_blue.svg"
    import cube_blue2 from "./cube_blue2.svg"
    import plumber from "../../assets/plumber.svg"
    import message from "../../assets/message_blue.svg"
    import phone from "../../assets/phone.svg"
    import location from "../../assets/location.svg"
    import Form from "../Form.svelte"

    export let id = ""

    let title = {
        section:"Contacts",
        slogan:"Get in Touch Today",
        id
    }
</script>

<aside>
    <SectionTitle props={title}/>
    <div class="contacts-div observer-class">
        <section class="section-left">
            <h3>Contact Us</h3>
            <p>Tell us about your problem and left contact information</p>
            <div class="form_container">
                <Form/>
            </div>
        </section>
        <span class="separator"></span>
        <section class="section-right">
            <h3>We are Ready to Help!</h3>
            <img src={plumber} alt="plumber"/>
            <div class="contact-info-div">
                <section>
                    <img src={message} alt="message"/>
                    <p>bradplumbing.ko@gmail.com</p>
                </section>
                <section>
                    <img src={phone} alt="phone"/>
                    <p>+1(970)-573-0174</p>
                </section>
                <section>
                    <img src={phone} alt="phone"/>
                    <p>+1(970)-518-5714</p>
                </section>
                <section>
                    <img src={location} alt="location"/>
                    <p>Estes Park, CO. 80517</p>
                </section>
            </div>
        </section>
    </div>
    <img src={cube_blue} class="cube blue" alt="cube"/>
    <img src={cube_blue2} class="cube blue2" alt="cube"/>
</aside>


<style>
    aside{
        padding: calc(var(--gap-xbig) * 5) 0;
        position: relative;
        overflow: hidden;
    }

    .contacts-div{
        display: flex;
        justify-content: center;
        border-radius: var(--border-rad);
        background: #ffffff;
        box-shadow: 20px 20px 60px #e8ecf0,
                    -2px -2px 40px #eff1f3;
        max-width: 62rem;
        margin: 0 auto;
        margin-top: calc(var(--gap-xbig) * 2);
    }
    
    .contact-info-div section{
        display: flex;
        gap: var(--gap-sm);
    }

    .section-left,
    .section-right{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        flex: 1;
        padding: var(--gap-xbig);
    }

    .section-right{
        border-top-right-radius: var(--border-rad);
        border-bottom-right-radius: var(--border-rad);
        background: linear-gradient(-90deg, rgba(255, 255, 255, 0) 0%, rgba(219, 235, 245, 0.5) 70%, #DAEAF5 90%, #DAEAF5 100%);
    }

    .section-left p{
        font-size: calc(var(--font-sm) / 1.15);
        font-weight: 400;
        color:  var(--secondery-fnt-clr);
        margin-bottom: var(--gap-sm);
    }
    .separator{
        display: block;
        width: 2px;
        min-height: 100%;
        background-color: var(--secondery-clr);
        opacity: 0.16;
    }

    .form_container{
        width: 26.25rem;
    }

    .blue{
        top: 20%;
        right: 0%;

    }

    .blue2{
        top: 70%;
        left: 0%;
    }


    @media( width <= 26.875rem ){
        .contacts-div{
            flex-direction: column-reverse;
            margin: calc(var(--gap-xbig) * 2);
            box-shadow: 20px 20px 50px #e8ecf04b,
            -2px -2px 30px #eff1f32d,
            1px 1px 1px #e8ecf0,
            -2px -2px 1px #eff1f3
            ;
        }  

        .form_container{
            width: 20.25rem;
        }

        .separator{
            display: block;
            width: 100%;
            min-height: 2px;
            background-color: var(--secondery-clr);
            opacity: 0.16;
        }

        .section-right{
            border-top-right-radius: var(--border-rad);
            border-top-left-radius: var(--border-rad);
            border-bottom-right-radius: none;
            background: linear-gradient(-90deg, rgba(255, 255, 255, 0) 0%, rgba(219, 235, 245, 0.5) 70%, #DAEAF5 90%, #DAEAF5 100%);
        }

        .blue2{
            top: 70%;
            left: 0%;
            width: 70%;
        }
    }



</style>