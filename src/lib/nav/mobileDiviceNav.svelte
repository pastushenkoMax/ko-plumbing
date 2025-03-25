<script>
    import phone from "../../assets/phone.svg"
    import NavButton from '../bottons/navButton.svelte'

    let input_ref
    let activeId = "home"

    function scrollToSection(id) {
        input_ref.checked = false
        const section = document.getElementById(id)
        if (section) {
            section.scrollIntoView({ behavior: 'smooth' })
        }
        activeId = id
    }

        function handleScroll() {
        const sections = document.querySelectorAll("section");
        let currentSectionId = null;

        sections.forEach(section => {
            const rect = section.getBoundingClientRect();
            // Check if the section is in the viewport (with a little offset)
            if (rect.top <= window.innerHeight / 10 && rect.bottom >= window.innerHeight / 10) {
                currentSectionId = section.id;
            }
        });

        if (currentSectionId) {
            activeId = currentSectionId;
        }
    }

    import { onMount } from 'svelte'
        onMount(() => {
        const options = {
            root: null,
            threshold: 0.3,
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.forEach(_class => {
                        if(_class.includes("home")){
                            activeId = "home"
                        }
                        if(_class.includes("about")){
                            activeId = "about"
                        }
                        if(_class.includes("services-container")){
                            activeId = "services"
                        }
                        if(_class.includes("contacts")){
                            activeId = "contacts"
                        }
                    })
                }
            })
        }, options)

        const sections = document.querySelectorAll(".observer-class")
        sections.forEach(section => {
            observer.observe(section)
        });
    });
</script>

<nav>
    <div id="menuToggle">
        <input bind:this={input_ref} type="checkbox" id="menuCheckbox" />
        <span></span>
        <span></span>
        <span></span>
        <ul id="menu">
            <li class:active={activeId === "home"}>
                <NavButton props={{ 
                    id: "home", 
                    text: "Home", 
                    class: "btn-with-padding", 
                    onClick: scrollToSection 
                }}/>
            </li>
            <li class:active={activeId === "about"}>
                <NavButton props={{ 
                    id: "about", 
                    text: "About", 
                    class: "btn-with-padding", 
                    onClick: scrollToSection 
                }}/>
            </li>
            <li class:active={activeId === "services"}>
                <NavButton props={{ 
                    id: "services", 
                    text: "Services", 
                    class: "btn-with-padding", 
                    onClick: scrollToSection 
                }}/>
            </li>
            <li class:active={activeId === "contacts"}>
                <NavButton props={{ 
                    img: phone, 
                    id: "contacts", 
                    text: "Contact Us",
                    class: "btn-with-padding", 
                    onClick: scrollToSection 
                }}/>
            </li>
            </ul>
            </div>
        </nav>
<style>


#menuToggle
{
    display: block;
    position: fixed;
    top: var(--gap-xbig);
    right: var(--gap-xbig);
    z-index: 1;
    -webkit-user-select: none;
    user-select: none;
}


#menuToggle input{
    display: block;
    width: 26px;
    height: 24px;
    position: absolute;
    top: 0;
    left: 0;
    cursor: pointer;
    opacity: 0;
    z-index: 2; 
    -webkit-touch-callout: none;
    }

#menuToggle span{
    display: block;
    width: 28px;
    height: 4px;
    margin-bottom: 4px;
    position: relative;
    background: var(--accent-clr);
    border-radius: 3px;
    z-index: 1;
    transform-origin: 2px 0px;
    transition: transform 0.3s cubic-bezier(0.77,0.2,0.05,1.0),
                background 0.3s cubic-bezier(0.77,0.2,0.05,1.0),
                opacity 0.45s ease;
}

#menuToggle span:first-child{
    transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2){
    transform-origin: 0% 100%;
}

#menuToggle input:checked ~ span{
    opacity: 1;
    transform: rotate(45deg) translate(-2px, -1px);
    background: var(--accent-clr);
}

#menuToggle input:checked ~ span:nth-last-child(3){
    opacity: 0;
    transform: rotate(0deg) scale(0.2, 0.2);
}

#menuToggle input:checked ~ span:nth-last-child(2){
    transform: rotate(-45deg) translate(0, -1px);
}

#menu{
    position: absolute;
    padding: 0 var(--gap-xbig);
    top: calc(0% - var(--gap-xbig));
    left: calc(100% + var(--gap-xbig));
    width: 100vw;
    background: #ffffff;
    box-shadow: 20px 20px 40px #414141a9,
            1px 1px 1px #dadada;
    -webkit-font-smoothing: antialiased;
    transform-origin: 0% 0%;
    transform: translate(100%, 0);
    transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
}

#menu li{
    padding: 10px 0;
    font-size: 22px;
}


#menuToggle input:checked ~ ul{
    transform: none;
    transform: translate(-100%, 0);
}

:global(li.active > button){
        color: var(--secondery-clr);
    }

</style>