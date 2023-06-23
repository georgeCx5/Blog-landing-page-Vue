<script>
// import Arrow from '@/assets/images/icon-arrow-light.svg?component';

export default {
   data() {
      return {
         isOpened: false,
         isHovered: false,
         data: [
            {
               header: 'Product',
               links: [
                  'Overview',
                  'Pricing',
                  'Marketplace',
                  'Features',
                  'Integrations'
               ]
            },
            {
               header: 'Company',
               links: [
                  'About',
                  'Team',
                  'Blog',
                  'Careers'
               ]
            },
            {
               header: 'Connect',
               links: [
                  'Contact',
                  'Newsletter',
                  'LinkedIn'
               ]
            },
         ]
      }
   },
   props: {
      dataIndex: {
         Number,
         default: 0,
      }
   },
   components: {
      // Arrow,
   },
   computed: {
      arrowState() {
         return this.isOpened ? 'rotate-180' : '';
      },
      hoverState() {
         return this.isHovered ? 1 : .75;
      }
   }
}
</script>
<template>
   <button @click="isOpened = !isOpened" @mouseenter="isHovered = true" @mouseleave="isHovered = false"
      class=" flex items-center gap-[6px] text-neo-white text-opacity-75 hover:text-opacity-100 hover:underline underline-offset-2 ">
      {{ data[dataIndex].header }}
      <svg :class="arrowState" xmlns="http://www.w3.org/2000/svg" width="10" height="7">
         <path fill="none" stroke="#FFF" stroke-width="2" :opacity="hoverState" d="M1 1l4 4 4-4" />
      </svg>
   </button>
</template>