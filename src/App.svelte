<script>
import './app.css'
import Home from './components/Home.svelte'
import Carousel from './components/Carousel.svelte'
import EventDetails from './components/EventDetails.svelte'
</script>

<main class="w-screen min-h-screen flex justify-center bg-amber-50">
  <div class="container p-4">
    <Home />
    <Carousel />
    <EventDetails />
  </div>
</main>

<style>
</style>
