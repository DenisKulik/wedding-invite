<script>
import { onMount } from 'svelte'
import hands from '../assets/hands.webp'

const targetDate = new Date('2025-08-18T15:00:00').getTime()
let timeLeft = calculateTimeLeft()

function calculateTimeLeft() {
  const now = new Date().getTime()
  const difference = targetDate - now

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
  const interval = setInterval(() => {
    timeLeft = calculateTimeLeft()
  }, 1000)

  return () => clearInterval(interval)
})
</script>

<section class="flex justify-center">
  <div
    class="flex flex-col items-center justify-center w-full min-h-96 relative p-2"
  >
    <div
      class="absolute inset-0 bg-cover bg-center opacity-50"
      style="background-image: url({hands});"
    ></div>

    <div class="relative max-w-96 z-10 text-center">
      <h1 class="text-2xl md:text-5xl font-bold mb-10">
        До встречи в августе через:
      </h1>

      <div class="flex gap-4 text-2xl md:text-4xl font-mono">
        <div class="p-4 bg-neutral-50 bg-opacity-50 rounded-lg">
          <span>{timeLeft.days}</span>
          <p class="text-sm md:text-lg">Дней</p>
        </div>
        <div class="p-4 bg-neutral-50 bg-opacity-50 rounded-lg">
          <span>{timeLeft.hours}</span>
          <p class="text-sm md:text-lg">Часов</p>
        </div>
        <div class="p-4 bg-neutral-50 bg-opacity-50 rounded-lg">
          <span>{timeLeft.minutes}</span>
          <p class="text-sm md:text-lg">Минут</p>
        </div>
        <div class="p-4 bg-neutral-50 bg-opacity-50 rounded-lg">
          <span>{timeLeft.seconds}</span>
          <p class="text-sm md:text-lg">Секунд</p>
        </div>
      </div>
    </div>
  </div>
</section>
