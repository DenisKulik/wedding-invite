<script>
import { inview } from 'svelte-inview'
import house from '../assets/house.webp'
import AnimatedContainer from '../components/AnimatedContainer.svelte'
import Heading from '../components/Heading.svelte'
import Container from '../components/Container.svelte'

let inView = false
</script>

<section
  class="flex flex-col justify-center items-center mb-10"
  use:inview={{ unobserveOnEnter: true, rootMargin: '-10%' }}
  on:change={({ detail }) => (inView = detail.inView)}
>
  <AnimatedContainer {inView}>
    <Heading>Локация</Heading>
    <img src={house} alt="house" class="max-w-96 w-full mb-5 object-cover" />
    <p class="max-w-96 text-xl text-center italic mb-5">
      База отдыха «Пасека», Деревня Старый Шалай, 1 Юргинский муниципальный
      округ, Кемеровская область
    </p>
    <Container class="flex justify-center">
      <iframe
        src="https://yandex.ru/map-widget/v1/?um=constructor%3Aed617a264a76a0a32ca4fd9039bcd1102e877753d20d323e7a3a982b6ec292aa&amp;source=constructor"
        width="100%"
        height="300"
        frameborder="0"
      ></iframe>
    </Container>
  </AnimatedContainer>
</section>
