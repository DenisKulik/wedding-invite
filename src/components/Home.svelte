<script>
import denisPhoto from '../assets/denis.webp'
import annaPhoto from '../assets/anna.webp'
import dove from '../assets/dove.png'
import weddingRing from '../assets/wedding-ring.png'
</script>

<section class="flex flex-col items-center mb-28 pt-24">
  <div class="w-96 relative flex items-center justify-center mb-44">
    <img src={dove} alt="dove" class="absolute w-28 top-0 right-4" />
    <img
      src={weddingRing}
      alt="weddingRing"
      class="absolute w-20 bottom-0 left-12 translate-y-24"
    />

    <div
      class="bg-white p-4 shadow-lg rounded-lg border w-52 transform -rotate-6"
    >
      <img src={denisPhoto} alt="Дениска" class="w-full h-auto rounded-lg" />
      <p class="text-center text-lg font-handwriting mt-2">Дениска</p>
    </div>

    <div
      class="bg-white p-4 shadow-lg rounded-lg border w-52 transform rotate-6 translate-y-28"
    >
      <img src={annaPhoto} alt="Анечка" class="w-full h-auto rounded-lg" />
      <p class="text-center text-lg font-handwriting mt-2">Анечка</p>
    </div>
  </div>

  <h2 class="mb-7 text-center text-4xl font-handwriting">
    Узнаете этих малышей?
  </h2>
  <div class="text-center text-2xl text-gray-500">
    <p class="mb-5">
      Да-да, это мы! Время пролетело очень быстро, представляете?
    </p>
    <p>
      Мы рады пригласить Вас на торжество по случаю нашей свадьбы и разделить
      этот счастливый момент с нами!
    </p>
  </div>
</section>
