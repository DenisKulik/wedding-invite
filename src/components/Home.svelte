<script>
import { fade, fly } from 'svelte/transition'
import { onMount } from 'svelte'
import denisPhoto from '../assets/denis.webp'
import annaPhoto from '../assets/anna.webp'
import dove from '../assets/dove.png'
import weddingRing from '../assets/wedding-ring.png'

let showArrow = true
let sectionHeight = 0

const handleScroll = () => {
  showArrow = window.scrollY <= sectionHeight / 4
}

onMount(() => {
  window.addEventListener('scroll', handleScroll)
  return () => window.removeEventListener('scroll', handleScroll)
})
</script>

<section
  class="flex flex-col items-center min-h-screen mb-10 pt-24 overflow-hidden relative"
  bind:clientHeight={sectionHeight}
>
  <div class="w-96 relative flex items-center justify-center mb-44">
    <img
      src={dove}
      alt="dove"
      class="absolute w-28 top-0 right-4"
      transition:fade={{ duration: 1000, delay: 500 }}
    />
    <img
      src={weddingRing}
      alt="weddingRing"
      class="absolute w-20 bottom-0 left-12 translate-y-24"
      transition:fade={{ duration: 1000, delay: 500 }}
    />

    <div
      class="bg-white p-4 shadow-lg rounded-lg border w-52 transform -rotate-6"
      transition:fly={{ duration: 1000, x: -150 }}
    >
      <img
        src={denisPhoto}
        alt="Дениска"
        class="w-full min-h-44 h-auto rounded-lg"
      />
      <p class="text-center text-2xl font-handwriting font-bold mt-2">
        Дениска
      </p>
    </div>

    <div
      class="bg-white p-4 shadow-lg rounded-lg border w-52 transform rotate-6 translate-y-28"
      transition:fly={{ duration: 1000, x: 150 }}
    >
      <img
        src={annaPhoto}
        alt="Анечка"
        class="w-full min-h-44 h-auto rounded-lg"
      />
      <p class="text-center text-2xl font-handwriting font-bold mt-2">Анечка</p>
    </div>
  </div>

  <div transition:fade={{ duration: 1000, delay: 500 }}>
    <h2 class="mb-7 text-center text-4xl">Узнаете этих малышей?</h2>
    <div class="text-center text-2xl text-gray-600">
      <p class="mb-5">
        Да-да, это мы! Время пролетело очень быстро, представляете?
      </p>
      <p>
        Мы рады пригласить Вас на торжество по случаю нашей свадьбы и разделить
        этот счастливый момент с нами!
      </p>
    </div>
  </div>

  {#if showArrow}
    <div class="absolute bottom-8 left-1/2 -ml-5 animate-bounce">
      <svg
        class="w-10 h-10 text-gray-400"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M19 9l-7 7-7-7"
        />
      </svg>
    </div>
  {/if}
</section>
