<script lang="ts">
  import NavBar from "./lib/nav/NavBar.svelte"
  import SecondaryNavBar from "./lib/nav/SecondaryNavBar.svelte"
  import MobileDiviceNav from "./lib/nav/mobileDiviceNav.svelte"
  import Hero from "./lib/hero/Hero.svelte"
  import About from "./lib/about/About.svelte"
  import Services from "./lib/services/Services.svelte"
  import Contacts from "./lib/contacts/Contacts.svelte"
  import Footer from "./lib/footer/Footer.svelte"

  let showSecondaryNav = false

</script>

<svelte:window onscroll={() => showSecondaryNav = window.scrollY > 20} />

<main>
  <div class="mobile-nav-wrapper">
    <MobileDiviceNav/>
  </div>
  {#if showSecondaryNav}
    <div class="second-nav-wrapper">
      <SecondaryNavBar />
    </div>
  {/if}
  <div class="top">
    <NavBar/>
    <Hero id="home"/>
  </div>
  <About id="about"/>
  <Services id="services"/>
  <Contacts id="contacts"/>
</main>
<Footer/>

<style>
  .top{
    background: linear-gradient(180deg, #DAEAF5 0%, rgba(218, 234, 245, 0.7) 19.44%, rgba(255, 255, 255, 0) 100%);
  }

  .mobile-nav-wrapper{
    display: none;
  }

  /* Tablets and phones: hamburger menu instead of the two desktop navs. */
  @media( width <= 66rem ){
    .second-nav-wrapper{
      display: none;
    }
    .mobile-nav-wrapper{
      display: block;
    }
  }
</style>

