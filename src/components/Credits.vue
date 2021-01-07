<template>
  <div >
      
    <div class="mx-10 xl:max-w-screen-xl m-auto text-gray-600">  
        <div v-for="credit in mycredits" :key="credit"> 
            <div class="flex justify-between">
                <h3 class="text-2xl my-2 mx-6">{{credit.簡述}}</h3>
                <div class="flex align-middle justify-start w-40">
                    <h3 class="text-2xl mx-6">{{credit.分類}}</h3>
                    <button  v-if="credit.案由 != ''" @click="credit.isOpen = !credit.isOpen"  class="text-gray-500 hover:text-black focus:text-black pb-3">
                        <svg  class="h-6 w-6 fill-current" viewBox="-2.5 -5 75 60" preserveAspectRatio="none">
                            <path d="M0,0 l35,50 l35,-50" fill-rule="evenodd" stroke-width="5" />
                        </svg>
                    </button>
                </div>

            </div>
            <div v-if="credit.isOpen" class="mx-4 mb-6">
                <p class="text-gray-400"> {{credit.日期}} </p>
                <p> {{credit.案由}} </p>
            </div>
        </div>
    </div>
      
  </div>
</template>

<script>
import credits from '../../public/csvjson.json'
export default {
    name: "Credits",
    data(){
        return{
            mycredits: credits,
            
        }
    },

    
    
}
</script>

<style>

</style>