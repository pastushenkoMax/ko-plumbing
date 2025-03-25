<script>
    import phone from "../../assets/phone.svg"
    import NavButton from '../bottons/navButton.svelte'

    let activeId = "home"
    let open = true

    function scrollToSection(id) {
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

        // Observe each section
        const sections = document.querySelectorAll(".observer-class")
        sections.forEach(section => {
            observer.observe(section)
        });
    });
</script>

<nav>
    <ul>
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
</nav>


<style>

    nav {
        position: fixed;
        top: var(--gap-sm);
        left: 50%;
        transform: translate(-50%, 0);
        border-radius: var(--border-rad);
        box-shadow: 4px 4px 4px #a3c7db50,
                    -1px -1px 5px #65656865;
        display: flex;
        justify-content: space-between;
        align-items: center;
        z-index: 1000;
        background: rgba(255, 255, 255);
        transition: transform 0.3s ease-in-out;
    }

    ul {
        display: flex;        
    }

    li {
        font-size: var(--font-sm);
        font-weight: bold;
        text-align: center;
        border-left: 1px solid rgb(149, 202, 233);
        background: rgba(255, 255, 255);
        white-space: nowrap;
    }



    li:nth-child(1) {
        border-left: none;
        border-top-left-radius: var(--border-rad);
        border-bottom-left-radius: var(--border-rad);
    }
    li:nth-last-child(1) {
        border-top-right-radius: var(--border-rad);
        border-bottom-right-radius: var(--border-rad);
    }
    li:hover{
        filter: brightness(95%);

    }
    li.active {
        background: rgba(0, 152, 253, 0.226);
    }

    @media( width <= 26.875rem ){

    }
</style>