<script setup>
import { ref } from 'vue'

const regions = ref(['All regions', 'Bangkok city center', 'Su Weikun'])
const selectedRegion = ref('All regions')
const product = ref([
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Bangkok' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Su Weikun' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Bangkok' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Su Weikun' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Su Weikun' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Bangkok' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Bangkok' },
    { name: 'Paraffin treatment for 2 hands, 1 time at Adora Hair salon 1 time at Adora Hair salon Hair salon Hair salon', location: 'Bangkok Beauty ViMUT Hospital', newPrice: '1200', oldprice: '1,500', picture: '/carousel-item.jpg', distance: 1.6, region: 'Bangkok' },
])
const showAllProducts = ref(false)

function toggleShowAll() {
    showAllProducts.value = !showAllProducts.value; // Toggle the flag
}

function selectRegion(region) {
    selectedRegion.value = region
}
</script>

<template>
    <div>
        <div class="flex space-x-4">
            <button v-for="(region, index) in regions" :key="index" @click="selectRegion(region)"
                class="px-4 py-2 rounded-md relative"
                :class="selectedRegion === region ? 'bg-[#6E91E7] text-white' : 'bg-gray-200 text-gray-700 hover:bg-gray-300'">
                {{ region }}
                <span v-if="selectedRegion === region"
                    class="absolute -bottom-[6px] left-1/2 transform -translate-x-1/2 w-0 h-0 border-l-[10px] border-l-transparent border-r-[10px] border-r-transparent border-t-[10px] border-t-[#6E91E7]">
                </span>
            </button>
        </div>
        <div v-if="selectedRegion === 'All regions'" class="rounded-lg bg-[#FDEEF3] mt-4 pt-4">
            <div class="p-[2vh]">
                <p class="text-lg text-[#3A073D] font-bold">Large medical examination package</p>
                <p class="text-md text-[#3A073D] pt-[2vh] pb-[2vh]">
                    The bivalent HPV vaccine targets HPV 16 and 18, the main causes of cervical cancer.
                </p>
                <button class=" p-[1vh] rounded-full bg-white text-xs">View more information ></button>
            </div>
            <div class="bg-gradient-to-b rounded-lg from-white/70 to-white">
                <div class=" grid grid-cols-2 gap-3 p-[1vh]">
                    <div v-for="(product, index) in (showAllProducts ? product : product.slice(0, 4))" :key="index">
                        <div class=" shadow-lg bg-white rounded-lg p-[1vh]">
                            <div class="flex pb-[1vh]">
                                <p class=" w-[80%]">{{ product.name }}</p>
                                <img :src="product.picture" class=" w-12 rounded-lg" alt="image">
                            </div>
                            <div class="flex-col items-center ">
                                <div class="relative flex items-center justify-end">
                                    <div
                                        class="bg-gradient-to-r from-pink-500 to-orange-500 text-white text-sm px-3 py-1 rounded-full flex items-center relative">
                                        {{ product.newPrice }} THB
                                        <span class="ml-2">➔</span>

                                        <!-- Triangle -->
                                        <span
                                            class="absolute -bottom-1 left-1/2 transform -translate-x-1/2 w-0 h-0 border-l-[6px] border-l-transparent border-r-[6px] border-r-transparent border-t-[6px] border-t-pink-500">
                                        </span>
                                    </div>
                                </div>

                                <span class="text-gray-400 line-through mr-2">{{ product.oldprice }} THB</span>

                                <div
                                    class="flex-1 relative h-[2px] bg-gradient-to-r from-pink-300 via-pink-200 to-transparent mx-2">
                                    <span class="absolute -top-1 left-0 w-3 h-3 bg-pink-300 rounded-full"></span>
                                    <span class="absolute -top-1 right-0 w-3 h-3  left-1/1 bg-pink-500 rounded-full"></span>
                                </div>

                            </div>
                            <div class="flex justify-between pt-[2vh]">
                                <div class=" flex gap-2">
                                    <img src="/favicon.ico" alt="logo histpital" class="w-[2px] h-[2px]">
                                    <p class=" text-[#879399] text-xs">{{ product.location }}</p>
                                </div>
                                <div class="gap-1">
                                    <img src="/hdmall.png" alt="logo histpital" class="w-[2px] h-[2px]">
                                    <p class=" text-[#879399] text-xs">{{ product.distance }} km</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="product.length > 4" class="p-4">
                    <button @click="toggleShowAll" class="bg-white shadow-lg btn rounded-full w-full">
                        {{ showAllProducts ? 'Show less &#x25B2;' : 'View all &#x25BC;' }}
                    </button>
                </div>
            </div>
        </div>
        <div v-if="selectedRegion === 'All regions'" class="rounded-lg bg-[#FDEEF3] mt-4 pt-4">
            <div class="p-[2vh]">
                <p class="text-lg text-[#3A073D] font-bold">Large medical examination package</p>
                <p class="text-md text-[#3A073D] pt-[2vh] pb-[2vh]">
                    The bivalent HPV vaccine targets HPV 16 and 18, the main causes of cervical cancer.
                </p>
                <button class=" p-[1vh] rounded-full bg-white text-xs">View more information ></button>
            </div>
            <div class="bg-gradient-to-b rounded-lg from-white/70 to-white">
                <div class=" grid grid-cols-2 gap-3 p-[1vh]">
                    <div v-for="(product, index) in (showAllProducts ? product : product.slice(0, 4))" :key="index">
                        <div class=" shadow-lg bg-white rounded-lg p-[1vh]">
                            <div class="flex pb-[1vh]">
                                <p class=" w-[80%]">{{ product.name }}</p>
                                <img :src="product.picture" class=" w-12 rounded-lg" alt="image">
                            </div>
                            <div class="flex-col items-center ">
                                <div class="relative flex items-center justify-end">
                                    <div
                                        class="bg-gradient-to-r from-pink-500 to-orange-500 text-white text-sm px-3 py-1 rounded-full flex items-center relative">
                                        {{ product.newPrice }} THB
                                        <span class="ml-2">➔</span>

                                        <!-- Triangle -->
                                        <span
                                            class="absolute -bottom-1 left-1/2 transform -translate-x-1/2 w-0 h-0 border-l-[6px] border-l-transparent border-r-[6px] border-r-transparent border-t-[6px] border-t-pink-500">
                                        </span>
                                    </div>
                                </div>

                                <span class="text-gray-400 line-through mr-2">{{ product.oldprice }} THB</span>

                                <div
                                    class="flex-1 relative h-[2px] bg-gradient-to-r from-pink-300 via-pink-200 to-transparent mx-2">
                                    <span class="absolute -top-1 left-0 w-3 h-3 bg-pink-300 rounded-full"></span>
                                    <span class="absolute -top-1 right-0 w-3 h-3  left-1/1 bg-pink-500 rounded-full"></span>
                                </div>

                            </div>
                            <div class="flex justify-between pt-[2vh]">
                                <div class=" flex gap-2">
                                    <img src="/favicon.ico" alt="logo histpital" class="w-[2px] h-[2px]">
                                    <p class=" text-[#879399] text-xs">{{ product.location }}</p>
                                </div>
                                <div class="gap-1">
                                    <img src="/hdmall.png" alt="logo histpital" class="w-[2px] h-[2px]">
                                    <p class=" text-[#879399] text-xs">{{ product.distance }} km</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="product.length > 4" class="p-4">
                    <button @click="toggleShowAll" class="bg-white shadow-lg btn rounded-full w-full">
                        {{ showAllProducts ? 'Show less &#x25B2;' : 'View all &#x25BC;' }}
                    </button>
                </div>
            </div>
        </div>
        <div v-if="selectedRegion === 'Bangkok city center'">
            <div class=" text-center p-[2vh]">
                No content in bangkok

            </div>
        </div>
        <div v-if="selectedRegion === 'Su Weikun'">
            <div class=" text-center p-[2vh]">
                No content in bangkok

            </div>
        </div>

    </div>
</template>

<style lang="css" scoped></style>
