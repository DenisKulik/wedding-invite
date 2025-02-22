<script>
import house from '../assets/house.webp'

let map

DG.then(function () {
  map = DG.map('map', {
    center: [55.591868, 84.871967],
    zoom: 11,
  })

  DG.marker([55.591868, 84.871967]).addTo(map)
})
</script>

<section class="flex flex-col justify-center items-center mb-10">
  <h2 class="text-3xl font-bold text-gray-800 mb-5">Локация</h2>
  <img src={house} alt="house" class="max-w-96 w-full mb-5 object-cover" />
  <p class="max-w-96 text-l text-center italic mb-5">
    База отдыха «Пасека», Деревня Старый Шалай, 1 Юргинский муниципальный округ,
    Кемеровская область
  </p>
  <div id="map" class="w-full max-w-96 h-52"></div>
</section>
