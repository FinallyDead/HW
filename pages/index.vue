<template>
 <div 
  class="flex flex-col relative mx-auto  md:p-[60px] gap-y-[44px] md:w-[1024px] h-fit font-[Google_fonts] text-[#F2F2F2]
  min-[100px]:max-[767px]:p-[10px] min-[100px]:max-[767px]:pb-[37px] min-[100px]:max-[767px]:w-screen
  "
 >

  <div 
    class="absolute bg-[#6C846C] rounded-full w-[76px] h-[76px] md:top-[28%] md:left-[22px]  z-20
      min-[100px]:max-[767px]:top-[26%]  min-[100px]:max-[767px]:left-[-28px]
    "
  >
  </div>
  <div 
    class="absolute border-[#DDE0CD] border-[4px] rounded-full w-[99px] h-[99px] md:top-[1%] md:right-[19px] z-20
    min-[100px]:max-[767px]:left-[90%] min-[100px]:max-[767px]:top-[-48px]
    "
  >
  </div>
  <div 
    class="absolute bg-[#BCCCAF] rounded-full w-[35px] h-[36px] md:top-[447px] md:left-[54%] z-0
    min-[100px]:max-[767px]:z-20 min-[100px]:max-[767px]:top-[35%] min-[100px]:max-[767px]:left-[82%]
    "
  >
  </div>
  <div 
    class="absolute bg-[#183022] rounded-full w-[35px] h-[36px] md:top-[737px] md:left-[202px] z-0
    min-[100px]:max-[767px]:top-[58%] min-[100px]:max-[767px]:left-[15%]
    "
  >
  </div>
  <div 
    class="absolute bg-[#AFB982] rounded-full w-[45px] h-[46px] md:top-[845px] md:right-[72px] z-20
    min-[100px]:max-[767px]:top-[93%] min-[100px]:max-[767px]:left-[81%]
    "
  >
  </div>

    <div 
      class="flex md:gap-[24px] h-fit z-10
      min-[100px]:max-[767px]:flex-col
      "
    >
      <div 
        class="w-full md:rounded-[10px] flex flex-col main-gradient
        bg-no-repeat bg-[right_-90px_bottom_-30px] bg-[length:835px_1000px]
        px-[30px] py-[36px]
        min-[100px]:max-[767px]:rounded-t-[10px] min-[100px]:max-[767px]:h-[400px] 
        "
      >
        <label 
          class="text-[30px]"
        >
          20-22 сентября
        </label>
        <div 
          class="flex md:justify-between md:mt-auto text-[40px] font-[700] leading-none
          min-[100px]:max-[767px]:flex-col
          "
        >
          <NuxtLink 
            to="/fest"
          >
            <label 
              class="cursor-pointer"
            >
              Фестиваль<br> фермеских товаров
            </label>
          </NuxtLink>
          <NuxtLink 
            to="/fest"
          >
            <MdiIcon 
              size="60px" 
              icon="mdiArrowRight" 
              class="min-[100px]:max-[767px]:mt-[30px]"
            />
          </NuxtLink>
        </div>  
      </div>
      <div 
        class="md:w-[260px] min-h-[260px] h-fit md:rounded-[10px] px-[25px] pt-[36px] pb-[30px]
        bg-top bg-no-repeat bg-cover bg-[url('/assets/0bffa1818df549da5645525380b542ae.png')]
        min-[100px]:max-[767px]:rounded-b-[10px] min-[100px]:max-[767px]:w-full
        "
      >
        <p 
          class="text-[30px] mb-[7px]"
        >
          А также:
        </p>
        
        <h2 
          class="text-[30px] font-[700] mb-[17px] leading-none"
        >
          Выставка тыкв
        </h2>
        
        <label 
          v-if="viewport.isGreaterOrEquals('md')"
          class="text-[16px] w-[210px] "
        >
          Местные фермеры <br> покажут свои самые <br> большие тыквы. Посоревнуются чья тыква тяжелее и крепче.
        </label>
        
        <NuxtLink 
          to="/about"
        >
          <div 
            class="flex mt-[44px] border-white border-[2px] px-[20px] py-[15px] md:w-[215px] h-[54px] rounded-[10px] tracking-widest justify-center leading-[19.36px]
            min-[100px]:max-[767px]:w-full
            "
          >
            ЕЩЕ О ВЫСТАВКЕ
          </div>
        </NuxtLink>
      </div>
    </div>
    <div
      class="h-fit"
    >
      <h2 
        class="text-[#183022] text-[40px] font-[700] mb-[30px]"
      >
        Что на прилавке
      </h2>
      <div  
        v-if="viewport.isGreaterOrEquals('md')"
        class="flex gap-[24.4px]"
      >
        <NuxtLink
          v-for="data in goodsData" 
          :to="`/goods/${data.id}`"
          class="z-10"
        >
          <goods   
            :key="data.id" 
            :data="data" 
          />
        </NuxtLink>
      </div>
      <div
        v-else
      >
        <Swiper
          :slidesPerView="3"
          :spaceBetween="30"
        >
          <SwiperSlide
            v-for="data in goodsData" 
            class="!w-fit"
          >
            <NuxtLink
              :to="`/goods/${data.id}`"
              class="w-fit block"
            >
              <goods   
                :key="data.id" 
                :data="data" 
              />
            </NuxtLink>
          </SwiperSlide>
        </Swiper>
      </div>
    </div>
  </div>
</template>

<script setup>

const goodsData = [
  {
    id: 0,
    title: 'Тыква',
    price: 500,
    img: '/81ebf642b6ff6b4a90b85e73c6c65a75.png'
  },
  {
    id: 1,
    title: 'Цветная капуста',
    price: 350,
    img: '/bf85fa392da4687bb0f59a2a1ec7b6f1.png'
  },
  {
    id: 2,
    title: 'Мята',
    price: 150,
    img: '/2c77a5b606fb29e3aec899cbdbc5989b.png'
  },
  {
    id: 3,
    title: 'Базилик',
    price: 450,
    img: '/e5d80b8c02e921bd66101e24f93a2ada.png'
  },
  {
    id: 4,
    title: 'Кабачок',
    price:  50,
    img: '/049a07d4e9aa4e14d1cb64a1095b3137.png'
  }
]
const viewport = useViewport()

</script>

<style scoped>
.main-gradient {
  background-image: url('/assets/0495348afb670176564a379ffa29bc78.png');
}
@media (min-width: 768px) {
  .main-gradient {
    background-image: linear-gradient(180deg, rgba(173, 180, 148, 0) 70%, #AEB595 100%), url('/assets/0495348afb670176564a379ffa29bc78.png');
  }
}
</style>