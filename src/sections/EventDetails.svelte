<script>
import AnimatedContainer from '../components/AnimatedContainer.svelte'
import { inview } from 'svelte-inview'
import Heading from '../components/Heading.svelte'
import Calendar from '../components/Calendar.svelte'
import Container from '../components/Container.svelte'

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
      <p class="text-2xl font-bold text-gray-800 mb-2">
        <span>18 августа 2025</span>
        <br />
        <span>15:00</span>
      </p>
      <Calendar selectedDay={18} firstDayOffset={4} daysInMonth={31} />
    </Container>
  </AnimatedContainer>
</section>
