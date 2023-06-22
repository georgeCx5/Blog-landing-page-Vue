<script>
import HeaderButtons from './components/HeaderButtons.vue';
import NavBarUpperBtn from './components/NavBarUpperBtn.vue';

import logo from '@/assets/images/logo.svg?url';
import IconHamburger from '@/assets/images/icon-hamburger.svg?component';
import IconClose from '@/assets/images/icon-close.svg?component';
export default {
  data() {
    return {
      logo,
      isBarOpen: false,
    }
  },
  components: {
    HeaderButtons,
    NavBarUpperBtn,

    IconHamburger,
    IconClose,
  }
}
</script>
<template>
  <body class=" flex flex-col items-center font-overpass">
    <header
      class=" flex flex-col gap-[108px] w-full max-w-[425px] pt-14 pb-[156px] bg-gradient-to-br from-neo-light-red to-neo-very-dark-blue text-neo-white rounded-es-[100px]">
      <nav class=" relative flex justify-between items-center px-6">
        <img class=" h-8 select-none" :src="logo" alt="logo" draggable="false">
        <div @click="isBarOpen = !isBarOpen" class=" cursor-pointer select-none">
          <IconHamburger v-show="!isBarOpen" />
          <IconClose v-show="isBarOpen" />
        </div>
        <div v-show="isBarOpen"
          class=" absolute flex flex-col gap-6 right-6 top-16 w-[85%] pt-6 pb-8 bg-neo-white rounded-[5px] drop-shadow-nav">
          <NavBarUpperBtn btn-text="Product" :data-index="0" />
          <NavBarUpperBtn btn-text="Company" :data-index="1" />
          <NavBarUpperBtn btn-text="Connect" :data-index="2" />
          <div class=" flex flex-col items-center gap-6">
            <div class=" w-[85%] h-[1px] bg-neo-nav-line"></div>
            <button
              class=" text-neo-very-dark-blue hover:text-neo-very-light-red text-[18px] leading-[28px] font-semibold rounded-[28px]">
              Login
            </button>
            <button
              class=" w-[137px] h-[48px] bg-gradient-to-br from-neo-very-light-red-two to-neo-light-red-two hover:bg-none hover:bg-neo-very-light-red text-[16px] leading-[18px] font-bold rounded-[28px]">
              Sign Up
            </button>
          </div>
        </div>
      </nav>
      <div class=" flex flex-col items-center gap-12 px-6">
        <div class=" flex flex-col gap-1 text-center">
          <h1 class=" text-[37px] leading-[43px] tracking-[-1.08px] font-semibold">
            A modern publishing platform
          </h1>
          <p class=" text-[18px] leading-[21px]">
            Grow your audience and build your online brand
          </p>
        </div>
        <div class=" flex gap-4 font-bold">
          <HeaderButtons btn-text="Start for Free" :is-main-btn="true" />
          <HeaderButtons btn-text="Learn More" />
        </div>
      </div>
    </header>
  </body>
</template>