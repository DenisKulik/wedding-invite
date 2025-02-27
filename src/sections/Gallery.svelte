<script>
import Carousel from 'svelte-carousel'
import { inview } from 'svelte-inview'
import AnimatedContainer from '../components/AnimatedContainer.svelte'
import photo1 from '../assets/photo-1.webp'
import photo2 from '../assets/photo-2.webp'
import photo4 from '../assets/photo-4.webp'
import Heading from '../components/Heading.svelte'
import Container from '../components/Container.svelte'

const photos = [photo1, photo4, photo2]
let inView = false
</script>

<section
  class="w-full flex flex-col justify-center items-center mb-10 p-2"
  use:inview={{ unobserveOnEnter: true, rootMargin: '-10%' }}
  on:change={({ detail }) => (inView = detail.inView)}
>
  <AnimatedContainer {inView}>
    <Heading>А это мы сейчас!</Heading>
    <Container>
      <Carousel
        autoplay={true}
        infinite={true}
        autoplayDuration={5000}
        duration={800}
        arrows={false}
      >
        {#each photos as photo}
          <img src={photo} alt="photo" class="object-cover" />
        {/each}
      </Carousel>
    </Container>
  </AnimatedContainer>
</section>
