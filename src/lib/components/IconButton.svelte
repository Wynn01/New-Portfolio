<script lang="ts">
  export let link: string;
  export let name: string;
  export let newTab: boolean = true;
</script>

{#if newTab}
  <a
    target="_blank"
    rel="noopener noreferrer"
   
    aria-label={name}
    href={link}
    on:click
  >
    <slot />
  </a>
{:else}
  <a on:click  aria-label={name} href={link}>
    <slot />
  </a>
{/if}
