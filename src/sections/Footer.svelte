<script>
import hands from '../assets/hands.webp'
import Container from '../components/Container.svelte'
import CountdownTimer from '../components/CountdownTimer.svelte'

const eventDate = '2025-08-18T15:00:00'
</script>

<section class="flex justify-center">
  <div
    class="flex flex-col items-center justify-center w-full min-h-96 relative p-2"
  >
    <div
      class="absolute inset-0 bg-cover bg-center opacity-50"
      style="background-image: url({hands});"
    ></div>

    <Container class="flex flex-col items-center relative z-10 text-center">
      <h3 class="text-3xl mb-10">До встречи в августе через:</h3>
      <CountdownTimer targetDate={eventDate} />
    </Container>
  </div>
</section>
