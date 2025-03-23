<script>
    import logo from '../../assets/logo.svg'
    import home from '../../assets/home.svg'
    import NavButton from '../bottons/navButton.svelte';

    function scrollToSection(id) {
        const section = document.getElementById(id);
        if (section) {
            section.scrollIntoView({ behavior: 'smooth' });
        }
    }

</script>

<nav>
    <img src={logo} class="logo" alt="logo" />
    <ul>
        <li class="active">
            <NavButton props={{
                id:"home",
                text: "Home",
                img:home,
                class: "btn-with-img",
                onClick:scrollToSection
            }}/>
        </li>
        <li>
            <NavButton props={{
                id:"about",
                text: "About",
                onClick:scrollToSection
            }}/>
        </li>
        <li>
            <NavButton props={{
                id:"services",
                text: "Services",
                onClick:scrollToSection
            }}/>
        </li>
        <li>
            <NavButton props={{
                id:"contacts",
                text: "Contact Us",
                class: "btn-with-bg",
                onClick:scrollToSection
            }}/>
    </ul>
</nav>

<style>
    nav{
        display: flex;
        padding: var(--gap-md)  calc(var(--gap-xbig) * 2.5);
        justify-content: space-between;
        /* position: sticky; 
        top: 0;
        z-index: 100;
        background-color: white; */

    }
    ul{
        font-weight: 600;
        display: flex;
        gap: var(--gap-md);
        align-items: center;

    }
    li{
        font-size: var(--font-sm);
        letter-spacing: 0.39em;
        display: flex;
        align-items: center;
        gap: var(--gap-sm);
        position: relative;
        height: fit-content;
        --underline_clr: var(--primary-fnt-clr);
        font-weight: 600;
        transition: all 0.3s;

    }

</style>