<script>
import { useDataStore } from '@/assets/stores/DataStore';
import { mapStores } from 'pinia';
import ArrowSVG from './ArrowSVG.vue';

export default {
   data() {
      return {
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
   computed: {
      ...mapStores(useDataStore),
      rotateState() {
         return this.dataStore.navBar[this.dataIndex] ? 'rotate-180' : '';
      },
      opacityState() {
         return this.isHovered ? 1 : .75;
      }
   },
   components: {
      ArrowSVG,
   }
}
</script>
<template>
   <div class=" relative flex items-center">
      <button @click="dataStore.setOpened(dataIndex)" @mouseenter="isHovered = true" @mouseleave="isHovered = false"
         class=" flex items-center gap-[4px] text-neo-white text-opacity-75 hover:text-opacity-100 hover:underline underline-offset-4 ">
         {{ data[dataIndex].header }}
         <ArrowSVG :rotate-val="rotateState" :opacity-val="opacityState" />
      </button>
      <div v-show="dataStore.navBar[dataIndex]"
         class=" absolute top-10 -left-4 flex flex-col w-[124px] px-4 py-2 bg-white font-normal rounded-[5px] z-20">
         <button class=" text-left text-neo-very-dark-gray-blue text-[15px] leading-[24px] hover:font-bold"
            v-for="element in data[dataIndex].links">
            {{ element }}
         </button>
      </div>
   </div>
</template>