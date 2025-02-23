<script>
import './app.css'
import Home from './components/Home.svelte'
import Carousel from './components/Carousel.svelte'
import EventDetails from './components/EventDetails.svelte'
import Location from './components/Location.svelte'
import Footer from './components/Footer.svelte'
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
