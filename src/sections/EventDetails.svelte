<script>
import AnimatedContainer from '../components/AnimatedContainer.svelte'
import { inview } from 'svelte-inview'
import Heading from '../components/Heading.svelte'
import Calendar from '../components/Calendar.svelte'
import Container from '../components/Container.svelte'
import time from '../assets/time.png'
import date from '../assets/calendar.png'

let inView = false
</script>

<section
  class="text-center"
  use:inview={{ unobserveOnEnter: true, rootMargin: '-10%' }}
  on:change={({ detail }) => (inView = detail.inView)}
>
  <AnimatedContainer {inView}>
    <Container>
      <Heading>Дата и время проведения</Heading>
      <div class="text-2xl font-bold text-gray-800 mb-2">
        <div class="flex justify-center items-center gap-2">
          <img src={date} alt="date" class="w-6" />
          <span>18 августа 2025</span>
        </div>
        <div class="flex justify-center items-center gap-2">
          <img src={time} alt="time" class="w-6" />
          <span>15:00</span>
        </div>
      </div>
      <Calendar selectedDay={18} firstDayOffset={4} daysInMonth={31} />
    </Container>
  </AnimatedContainer>
</section>
