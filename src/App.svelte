<script>
import './app.css'
import Home from './sections/Home.svelte'
import Carousel from './sections/Gallery.svelte'
import EventDetails from './sections/EventDetails.svelte'
import Location from './sections/Location.svelte'
import Footer from './sections/Footer.svelte'
</script>

<main class="w-screen min-h-screen flex justify-center bg-amber-50">
  <div class="container">
    <Home />
    <Carousel />
    <EventDetails />
    <Location />
    <Footer />
  </div>
</main>

<style>
</style>
