<script setup>
import ContentLeft from '@/components/ContentLeft.vue'
import ContentRight from '@/components/ContentRight.vue'

</script>

<template>
    <div class="flex px-[4vh] bg-purple-200 min-h-screen max-h-full p-[3vh]">
        <div class=" w-[35%] pr-[2vh]">
            <ContentLeft/>
        </div>
        <div class="  w-[65%] pl-[2vh]">
            <ContentRight/>
            <div class="overflow-hidden"></div>
        </div>
        
    </div>
</template>

<style lang="scss" scoped>

</style>