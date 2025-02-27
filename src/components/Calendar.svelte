<script>
export let selectedDay
export let firstDayOffset
export let daysInMonth

const days = Array.from({ length: daysInMonth }, (_, i) => i + 1)
const weekdays = ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс']
</script>

<div class="w-full mb-10 bg-neutral-50 p-4 shadow-lg rounded-lg">
  <div class="grid grid-cols-7 gap-1 text-gray-700">
    {#each weekdays as day}
      <div class="font-semibold">{day}</div>
    {/each}

    {#each Array(firstDayOffset).fill('') as _}
      <div></div>
    {/each}

    {#each days as day}
      <div
        class="w-8 h-8 flex items-center justify-center rounded-full
          {day === selectedDay
          ? 'bg-red-400 text-white font-bold'
          : 'hover:bg-gray-200'}"
      >
        {day}
      </div>
    {/each}
  </div>
</div>
