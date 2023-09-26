<script lang="ts">
  import "../app.css";
  import Navbar from "$lib/components/Navbar.svelte";
  import SEO from "svelte-seo";
</script>

<svelte:head>
  <SEO
    title="Pakorn Kanjanapan | Beginner-level Front-end developer"
    description="Pakorn Kanjanapan | Beginner-level Front-end developer"
    canonical=""
  />
</svelte:head>

<Navbar />
<main class="pt-16">
  <slot />
</main>
<footer class ="bg-neutral-100 text-center text-neutral-600 dark:bg-neutral-600 dark:text-neutral-200" >Made with Svelte</footer>
