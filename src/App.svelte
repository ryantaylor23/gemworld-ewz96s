<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Home from "./Home.svelte";
	import Gems from "./Gems.svelte";
	import Products from "./Products.svelte";
  import About from "./About.svelte";
  import Contact from "./Contact.svelte";
	
	export let menu = 1;
</script>

<main>
    <Header />
      <ul class="container-fluid parallax text-start bg-secondary p-3"id="menu">
        <li><a href="/" on:click|preventDefault={() => (menu = 1)}>Home</a></li> 
        <li><a href="/gems" on:click|preventDefault={() => (menu = 2)}>Gems</a></li> 
        <li><a href="/products" on:click|preventDefault={() => (menu = 3)}>Products</a></li>
        <li><a href="/about" on:click|preventDefault={() => (menu = 4)}>About</a></li>
        <li><a href="/contact" on:click|preventDefault={() => (menu = 5)}>Contact</a></li>
      </ul>

      {#if menu === 1}
      <Home />
      {:else if menu === 2}
      <Gems />
      {:else if menu === 3}
      <Products />
      {:else if menu === 4}
      <About />
      {:else if menu === 5}
      <Contact />
      {:else}
      <h1>
        404 Page Not Found
      </h1>
      {/if}

      <Footer />
</main>

<style>
	ul#menu li{
		list-style-type: none;
    display: flex;
    display: inline;
    margin-left: 20px;
    font-size: 20px;
	}
  main {
     color: white; 
     background-color: #91a3b0;
     width: 100vw;
  }
  a {
    color: white;
  }
  a:hover{
    color: black;
  }
 @media (max-width: 600px) {
  ul#menu li{
    display: block;
  }
}
</style>

