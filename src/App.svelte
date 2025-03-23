<script lang="ts">
  import NavBar from "./lib/nav/NavBar.svelte"
  import SecondaryNavBar from "./lib/nav/SecondaryNavBar.svelte"
  import Hero from "./lib/hero/Hero.svelte"
  import About from "./lib/about/About.svelte"
  import Services from "./lib/services/Services.svelte"
  import Contacts from "./lib/contacts/Contacts.svelte"


  import { onMount, onDestroy } from "svelte"

  let showSecondaryNav = false

  function handleScroll() {
    showSecondaryNav = window.scrollY > 20
  }

  onMount(() => {
    window.addEventListener("scroll", handleScroll)
  })

  onDestroy(() => {
    window.removeEventListener("scroll", handleScroll)
  })

</script>

<main>
  {#if showSecondaryNav}
    <SecondaryNavBar />
  {/if}
  <div class="top">
    <NavBar/>
    <Hero id="home"/>
  </div>
  <About id="about"/>
  <Services id="services"/>
  <Contacts id="contacts"/> 
</main>

<style>
  .top{
    background: linear-gradient(180deg, #DAEAF5 0%, rgba(218, 234, 245, 0.7) 19.44%, rgba(255, 255, 255, 0) 100%);
  }
</style>

