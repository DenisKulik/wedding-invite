<script>
import { fade, fly } from 'svelte/transition'
import { onMount } from 'svelte'
import denisPhoto from '../assets/denis.webp'
import annaPhoto from '../assets/anna.webp'
import dove from '../assets/dove.png'
import weddingRing from '../assets/wedding-ring.png'
import Heading from '../components/Heading.svelte'
import Container from '../components/Container.svelte'
import ScrollArrow from '../components/ScrollArrow.svelte'
import PersonCard from '../components/PersonCard.svelte'

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
  class="flex flex-col items-center min-h-screen mb-10 pt-4 overflow-hidden relative"
  bind:clientHeight={sectionHeight}
>
  <Container class="relative flex items-center justify-center mb-44">
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

    <PersonCard image={denisPhoto} alt="Дениска" tilt={-6}>Дениска</PersonCard>
    <div class="transform translate-y-28">
      <PersonCard image={annaPhoto} alt="Анечка" tilt={6}>Анечка</PersonCard>
    </div>
  </Container>

  <div class="text-center" transition:fade={{ duration: 1000, delay: 500 }}>
    <Heading>Узнаете этих малышей?</Heading>
    <div class=" text-2xl text-gray-600">
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
    <ScrollArrow />
  {/if}
</section>
