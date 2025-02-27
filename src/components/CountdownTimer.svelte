<script>
import { onMount, onDestroy } from 'svelte'

export let targetDate

let timeLeft = calculateTimeLeft()
let interval

function calculateTimeLeft() {
  const now = new Date().getTime()
  const difference = new Date(targetDate).getTime() - now

  if (difference <= 0) {
    return { days: 0, hours: 0, minutes: 0, seconds: 0 }
  }

  return {
    days: Math.floor(difference / (1000 * 60 * 60 * 24)),
    hours: Math.floor((difference / (1000 * 60 * 60)) % 24),
    minutes: Math.floor((difference / (1000 * 60)) % 60),
    seconds: Math.floor((difference / 1000) % 60),
  }
}

onMount(() => {
  interval = setInterval(() => {
    timeLeft = calculateTimeLeft()
  }, 1000)
})

onDestroy(() => {
  clearInterval(interval)
})
</script>

<div class="flex gap-4 text-3xl md:text-4xl">
  {#each Object.entries(timeLeft) as [unit, value]}
    <div class="p-4 bg-neutral-50 bg-opacity-50 rounded-lg">
      <span>{value}</span>
      <p class="text-lg">
        {unit === 'days'
          ? 'Дней'
          : unit === 'hours'
            ? 'Часов'
            : unit === 'minutes'
              ? 'Минут'
              : 'Секунд'}
      </p>
    </div>
  {/each}
</div>
