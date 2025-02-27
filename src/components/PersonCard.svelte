<script>
export let image
export let alt
export let tilt = 0

import { fly } from 'svelte/transition'
</script>

<div
  class="bg-white p-4 shadow-lg rounded-lg border w-52 {$$restProps.class}"
  style="transform: rotate({tilt}deg);"
  transition:fly={{ duration: 1000, x: tilt > 0 ? 150 : -150 }}
>
  <img
    src={image}
    {alt}
    class="w-full min-h-44 h-auto rounded-lg object-cover"
  />
  <p class="text-center text-2xl font-handwriting font-bold mt-2">
    <slot />
  </p>
</div>
