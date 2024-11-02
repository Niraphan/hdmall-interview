<script setup>
import { ref, computed } from 'vue';

const currentIndex = ref(0);
const items = ref([
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' },
    { image: '/carousel-item.jpg' }
]);

// Split items into chunks of 4 for each "slide"
const chunkedItems = computed(() => {
    const chunkSize = 4;
    const chunks = [];
    for (let i = 0; i < items.value.length; i += chunkSize) {
        chunks.push(items.value.slice(i, i + chunkSize));
    }
    return chunks;
});

function nextSlide() {
    currentIndex.value = (currentIndex.value + 1) % chunkedItems.value.length;
}

function prevSlide() {
    currentIndex.value = (currentIndex.value - 1 + chunkedItems.value.length) % chunkedItems.value.length;
}
</script>


<template>
    <div class="rounded-md bg-gradient-to-r from-[#F7EDF5] to-[#C7D2F3] shadow-lg">
        <div class="px-[2vh]">
            <p class=" text-[#2970CC] text-lg font-bold pt-[3vh]">Cancel Cancer</p>
            <p class=" text-[#4F579A] text-2xl font-bold pt-[2vh]"> Bangkok Medical <br> Examination</p>
            <p class=" text-md pt-[2vh]"> 9 Vacination Course 3 Needles <br> subitile text</p>
            <p class=" text-md pt-[2vh]"> One Price</p>
            <div class=" inline-flex items-baseline">
                <p class=" text-2xl font-bold text-[#4F579A] pr-[1vh]">16,999</p>
                <p class=" text-[#4F579A] text-lg "> THB</p>
            </div>
            <div class="relative w-full overflow-hidden ">
                <!-- Carousel Inner -->
                <div class="flex transition-transform duration-500 ease-in-out"
                    :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
                    <div v-for="(chunk, index) in chunkedItems" :key="index"
                        class="min-w-full flex justify-around items-center py-4">
                        <div v-for="(item, subIndex) in chunk" :key="subIndex"
                            class="w-20 h-40 rounded-lg overflow-hidden bg-gray-200 shadow-lg">
                            <img :src="item.image" alt="Carousel Image" class="w-full h-full object-cover" />
                            <div class="absolute inset-0 flex items-center justify-center">
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Controls -->
                <button @click="prevSlide"
                    class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-black bg-opacity-50 text-white p-2 rounded-full">
                    &#10094;
                </button>
                <button @click="nextSlide"
                    class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-black bg-opacity-50 text-white p-2 rounded-full">
                    &#10095;
                </button>
            </div>
        </div>
        <div>
            <div class="carousel carousel-center rounded-box space-x-4 p-4 mt-4 mx-auto max-w-[100%]">
                <div class="carousel-item">
                    <div class=" rounded-xl bg-white">
                        <p>"Safe, covenient, peace of mind"</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class=" rounded-xl bg-white">
                        <p>"Safe, covenient, peace of mind"</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class=" rounded-xl bg-white">
                        <p>"Safe, covenient, peace of mind"</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class=" rounded-xl bg-white">
                        <p>"Safe, covenient, peace of mind"</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class=" rounded-xl bg-white">
                        <p>"Safe, covenient, peace of mind"</p>
                    </div>
                </div>
                <div class="carousel-item">
                <div class=" rounded-xl bg-white">
                    <p>"Safe, covenient, peace of mind"</p>
                </div>
            </div>
        </div>
        <div class=" bg-[#89A6EB] rounded-b-lg  p-4">
            <div class="font-medium  text-md flex justify-between gap-3 pb-[2vh]">
                <div class="bg-white rounded-2xl h-7 flex items-center justify-center px-2">
                    <img src="/hdmall.png" alt="hdmall" class="rounded-xl h-5">
                </div>
                <p class=" text-white ">10,000 heath have been shared</p>
            </div>
            <div class=" flex justify-between">
                <div class=" bg-[#F7F3FF] rounded-lg text-[#4F579A] px-2">
                    <p> 0% interest</p>
                    <p> installment</p>
                </div>
                <div class=" bg-[#F7F3FF] rounded-lg text-[#4F579A] px-2">
                        <p> HDmall sold</p>
                        <p> 10,000 units</p>
                    </div>
                <div class=" bg-[#F7F3FF] rounded-lg text-[#4F579A] px-2">
                        <p> Real user</p>
                        <p> reviews</p>
                </div>
            </div>
        </div>

    </div>
</div></template>

<style lang="scss" scoped></style>