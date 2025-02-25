<script>
export let inView = false
</script>

<div
  class="transition-transform duration-700 ease-in-out translate-y-20 opacity-0"
  class:animate={inView}
>
  <slot />
</div>

<style>
.animate {
  transform: translateY(0);
  opacity: 1;
}
</style>
