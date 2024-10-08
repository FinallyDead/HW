<template>
  <div 
    class="flex flex-col text-[16px]  text-[#485F3B]  md:w-[161.6px] h-[277.83px] rounded-[10px] bg-white shadow-[0px_10px_10px_0px_#00000012]
      min-[100px]:max-[767px]:w-[40vw] min-[100px]:max-[480px]:h-[32vh] min-[480px]:max-[767px]:h-[50vh]
    "
  >
    <NuxtImg 
      :src="data.img"
      :width="computedWidth"
      :height="computedWidth"
      class="rounded-[10px]"
    />
    <div 
      class="flex flex-col h-full m-[16px]"
    > 
      <div
        class="max-h-[46px] truncate"
      >
        <label
          class="font-[400]"
          >
          {{ data.title }}
        </label>
      </div>
      <div 
        class="mt-auto"
      >
        <label 
          class="font-[700] "
        >
          {{ data.price }} ₽
        </label>
      </div>
    </div>
  </div>
</template>

<script setup>

const props = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const viewport = useViewport()

const computedWidth = computed(() => {
  let width = viewport.isGreaterOrEquals('md') ? 160 :  Math.trunc(window.innerWidth * 0.4)
  return width
})

const computedHeight = computed(() => {
  let height = viewport.isGreaterOrEquals('md') ? 160 : Math.trunc(window.innerHeight * 0.25)
  console.log(height)
  return height
})


</script>
