<script>
import Carousel from 'svelte-carousel'
import photo1 from '../assets/photo-1.webp'
import photo2 from '../assets/photo-2.webp'
import photo3 from '../assets/photo-3.webp'
import photo4 from '../assets/photo-4.webp'

const photos = [photo1, photo4, photo2, photo3]
</script>

<section class="w-full flex flex-col justify-center items-center mb-28">
  <p class="mb-5 text-3xl text-center">А это мы сейчас!</p>
  <div class="max-w-96 w-100%">
    <Carousel
      autoplay={true}
      infinite={true}
      autoplayDuration={5000}
      duration={1000}
      arrows={false}
    >
      {#each photos as photo}
        <img src={photo} alt="photo" class="object-cover" />
      {/each}
    </Carousel>
  </div>
</section>
