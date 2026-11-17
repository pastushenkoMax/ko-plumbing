<script>
    import logo from "../../assets/logo.svg"
    import message from "../../assets/message_blue.svg"
    import phone from "../../assets/phone.svg"
    import location from "../../assets/location.svg"

    const year = new Date().getFullYear()

    const links = [
        { href: "#home", text: "Home" },
        { href: "#about", text: "About" },
        { href: "#services", text: "Services" },
        { href: "#contacts", text: "Contact Us" },
    ]

    const services = ["Water Heaters", "Residential Plumbing", "New Construction"]
</script>

<footer>
    <div class="footer-grid">
        <section class="brand">
            <img src={logo} class="logo" alt="Knockout Plumbing & Heating" />
        </section>

        <nav aria-label="Footer">
            <h4>Company</h4>
            <ul>
                {#each links as l}
                    <li><a href={l.href}>{l.text}</a></li>
                {/each}
            </ul>
        </nav>

        <section>
            <h4>Services</h4>
            <ul>
                {#each services as s}
                    <li><a href="#services">{s}</a></li>
                {/each}
            </ul>
        </section>

        <section>
            <h4>Get in Touch</h4>
            <ul class="contact">
                <li>
                    <img src={phone} alt="" />
                    <a class="phone" href="tel:+19705730174">+1 (970) 573-0174</a>
                </li>
                <li>
                    <img src={phone} alt="" />
                    <a class="phone" href="tel:+19705185714">+1 (970) 518-5714</a>
                </li>
                <li>
                    <img src={message} alt="" />
                    <a href="mailto:bradplumbing.ko@gmail.com">bradplumbing.ko@gmail.com</a>
                </li>
                <li>
                    <img src={location} alt="" />
                    <span>Estes Park, CO 80517</span>
                </li>
            </ul>
        </section>
    </div>

    <div class="bottom-bar">
        <p>© {year} Knockout Plumbing & Heating. All rights reserved.</p>
        <a href="#home" class="to-top">Back to top ↑</a>
    </div>
</footer>

<style>
    footer{
        background: linear-gradient(180deg, rgba(255, 255, 255, 0) 0%, #DAEAF5 35%, #DAEAF5 100%);
        padding: calc(var(--gap-xbig) * 3) var(--page-gutter) var(--gap-xbig);
    }

    /* Brand column a bit wider; columns wrap naturally as space runs out. */
    .footer-grid{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(min(13rem, 100%), 1fr));
        gap: calc(var(--gap-xbig) * 1.5) var(--gap-xbig);
        max-width: 87.5rem;
        margin: 0 auto;
    }

    @media( width > 66rem ){
        .footer-grid{
            grid-template-columns: 1.6fr 1fr 1fr 1.3fr;
        }
    }

    .brand{
        display: flex;
        flex-direction: column;
        gap: var(--gap-md);
    }

    .logo{
        width: clamp(11rem, 8rem + 8vw, 16rem);
    }

    h4{
        font-size: var(--font-sm);
        font-weight: 900;
        letter-spacing: 0.3em;
        text-transform: uppercase;
        margin-bottom: var(--gap-big);
    }

    ul{
        display: flex;
        flex-direction: column;
        gap: var(--gap-md);
    }

    li{
        font-size: var(--font-sm);
        line-height: 1.4;
    }

    a{
        color: var(--secondery-fnt-clr);
        text-decoration: none;
        font-weight: 500;
        transition: color 0.2s;
    }

    a:hover,
    a:focus-visible{
        color: var(--primary-fnt-clr);
    }

    a:focus-visible{
        outline: 2px solid var(--secondery-clr);
        outline-offset: 2px;
        border-radius: 2px;
    }

    .contact li{
        display: flex;
        align-items: center;
        gap: var(--gap-sm);
    }

    .contact img{
        width: 1.1em;
        flex: none;
    }

    .contact a,
    .contact span{
        overflow-wrap: anywhere;
        color: var(--secondery-fnt-clr);
    }

    /* The one accent in the footer: phone numbers, the action that matters. */
    .contact a.phone{
        color: var(--primary-fnt-clr);
        font-weight: 700;
    }

    .contact a.phone:hover{
        color: var(--accent-clr);
    }

    .bottom-bar{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        gap: var(--gap-md);
        max-width: 87.5rem;
        margin: calc(var(--gap-xbig) * 2) auto 0;
        padding-top: var(--gap-xbig);
        border-top: 1px solid rgba(81, 163, 225, 0.25);
    }

    .bottom-bar p,
    .to-top{
        font-size: calc(var(--font-sm) * 0.85);
        color: var(--secondery-fnt-clr);
    }

    @media (prefers-reduced-motion: reduce){
        a{
            transition: none;
        }
    }
</style>
