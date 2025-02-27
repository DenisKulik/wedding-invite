<script>
export let level = 'h2'
</script>

<svelte:element this={level} class="mb-5 text-4xl text-center">
  <slot />
</svelte:element>
