<script>
const days = Array.from({ length: 31 }, (_, i) => i + 1)
const firstDayOffset = 4
</script>

<section class="flex flex-col items-center text-center">
  <h2 class="text-3xl font-bold text-gray-800 mb-5">Дата и время проведения</h2>

  <p class="text-xl font-bold text-gray-800 mb-2">
    18 августа 2025 <br />15:00
  </p>

  <div class="max-w-96 w-full bg-neutral-50 p-4 shadow-lg rounded-lg">
    <div class="grid grid-cols-7 gap-1 text-gray-700">
      <!-- Заголовки дней недели -->
      {#each ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'] as day}
        <div class="font-semibold">{day}</div>
      {/each}

      {#each Array(firstDayOffset).fill('') as _}
        <div></div>
      {/each}

      {#each days as day}
        <div
          class="w-8 h-8 flex items-center justify-center rounded-full
          {day === 18
            ? 'bg-red-400 text-white font-bold'
            : 'hover:bg-gray-200'}"
        >
          {day}
        </div>
      {/each}
    </div>
  </div>
</section>
