<script>
import HeaderButtons from './components/HeaderButtons.vue';
import NavBarUpperBtn from './components/NavBarUpperBtn.vue';
import SectionText from './components/SectionText.vue';

import logo from '@/assets/images/logo.svg?url';
import IconHamburger from '@/assets/images/icon-hamburger.svg?component';
import IconClose from '@/assets/images/icon-close.svg?component';
import BgMobile from '@/assets/images/bg-pattern-intro-mobile.svg?component';
import editorImgMB from '@/assets/images/illustration-editor-mobile.svg?url';
import phonesImgMB from '@/assets/images/illustration-phones.svg?url';
import laptopImgMB from '@/assets/images/illustration-laptop-mobile.svg?url';
import BgPatternCircles from '@/assets/images/bg-pattern-circles.svg?component';

export default {
  data() {
    return {
      logo,
      isBarOpen: false,
      editorImgMB,
      phonesImgMB,
      laptopImgMB,
      data: {
        one: [
          {
            header: 'Introducing an extensible editor',
            main: 'Blogr features an exceedingly intuitive interface which lets you focus on one thing: creating content. The editor supports management of multiple blogs and allows easy manipulation of embeds such as images, videos, and Markdown. Extensibility with plugins and themes provide easy ways to add functionality or change the looks of a blog.'
          },
          {
            header: 'Robust content management',
            main: 'Flexible content management enables users to easily move through posts. Increase the usability of your blog by adding customized categories, sections, format, or flow. With this functionality, you’re in full control.'
          }
        ],
        two: [
          {
            header: 'State of the Art Infrastructure',
            main: 'With reliability and speed in mind, worldwide data centers provide the backbone for ultra-fast connectivity. This ensures your site will load instantly, no matter where your readers are, keeping your site competitive.'
          }
        ]
        ,
        three: [
          {
            header: 'Free, open, simple',
            main: 'Blogr is a free and open source application backed by a large community of helpful developers. It supports  features such as code syntax highlighting, RSS feeds, social media integration, third-party commenting tools, and works seamlessly with Google Analytics. The architecture is clean and is relatively easy to learn.'
          },
          {
            header: 'Powerful tooling',
            main: 'Batteries included. We built a simple and straightforward CLI tool that makes customization and deployment a breeze, but capable of producing even the most complicated sites.'
          }
        ]
      }
    }
  },
  components: {
    HeaderButtons,
    NavBarUpperBtn,
    SectionText,

    IconHamburger,
    IconClose,
    BgMobile,
    BgPatternCircles,
  }
}
</script>
<template>
  <body class=" relative flex flex-col items-center font-overpass">
    <header
      class=" relative flex flex-col gap-[108px] w-full max-w-[425px] pt-14 pb-[156px] bg-gradient-to-br from-neo-very-light-red-two to-neo-light-red-two text-neo-white rounded-es-[100px] overflow-hidden">
      <BgMobile class=" absolute -left-[345px] -top-[260px]" />
      <nav class=" relative flex justify-between items-center px-6">
        <img class=" h-8 select-none" :src="logo" alt="logo" draggable="false">
        <div @click="isBarOpen = !isBarOpen" class=" cursor-pointer select-none">
          <IconHamburger v-show="!isBarOpen" />
          <IconClose v-show="isBarOpen" />
        </div>
        <div v-show="isBarOpen"
          class=" absolute flex flex-col gap-6 right-6 top-16 w-[85%] pt-6 pb-8 bg-neo-white rounded-[5px] drop-shadow-nav select-none z-20">
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
      <div class=" flex flex-col items-center gap-12 px-6 z-10">
        <div class=" flex flex-col gap-4 text-center">
          <h1 class=" text-[37px] leading-[43px] tracking-[-1.08px] font-semibold">
            A modern publishing platform
          </h1>
          <p class=" text-[18px] leading-[21px]">
            Grow your audience and build your online brand
          </p>
        </div>
        <div class=" flex gap-4 font-bold select-none">
          <HeaderButtons btn-text="Start for Free" :is-main-btn="true" />
          <HeaderButtons btn-text="Learn More" />
        </div>
      </div>
    </header>
    <main class=" max-w-[425px] py-[100px]">
      <section class=" flex flex-col gap-[38px] mb-[273px] px-6 text-neo-very-dark-blue">
        <h2 class=" text-center text-[28px] leading-[33px] tracking-[-.84px] font-semibold">
          Designed for the future
        </h2>
        <div class=" flex flex-col gap-[46px]">
          <img :src="editorImgMB" alt="editorImgMB" draggable="false">
          <div class=" flex flex-col gap-10 pl-[9px]">
            <SectionText :header="data.one[0].header" :main="data.one[0].main" />
            <SectionText :header="data.one[1].header" :main="data.one[1].main" />
          </div>
        </div>
      </section>
      <section class=" relative w-full h-[625px] mb-[79px]">
        <img class=" absolute -top-[180px] z-10" :src="phonesImgMB" alt="phonesImgMB">
        <div
          class=" relative w-full h-full bg-gradient-to-br from-neo-very-dark-gray-blue to-neo-very-dark-desaturated-blue rounded-se-[100px] rounded-es-[100px] overflow-hidden">
          <BgPatternCircles class=" absolute -left-[315px] -top-[460px] scale-[.6]" />
          <SectionText class=" relative mt-[221px] px-6 z-10" :header="data.two[0].header" :main="data.two[0].main"
            :is-special="true" />
        </div>
      </section>
      <section class=" flex flex-col gap-[46px] px-6">
        <img :src="laptopImgMB" alt="laptopImgMB" draggable="false">
        <div class=" flex flex-col gap-10 pl-[9px]">
          <SectionText :header="data.three[0].header" :main="data.three[0].main" />
          <SectionText :header="data.three[1].header" :main="data.three[1].main" />
        </div>
      </section>
    </main>
  </body>
</template>