<script setup>

</script>

<template>
    <div class="flex pl-[4vh] gap-5 pt-[3vh] align-middle pb-[3vh] font-medium">
        <img src="/hdmall.png" alt="hdlogo" class="w-[10vh]">
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient ">
            รายละเอียด
        </a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">สถานที่ให้บริการ</a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">HDReview</a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">รีวิวแพ็กเกจ</a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">คำถามจากผู้ใช้</a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">บทความเกี่ยวข้อง</a>
        <a href="/" class="relative hover:text-[#338BFF] underline-gradient">แพ็กเกจแนะนำ</a>
    </div>
</template>

<style>
.underline-gradient::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    height: 2px;
    width: 0;
    background: linear-gradient(to right, #06b6d4, #3b82f6);
    transition: width 0.3s ease;
    
}

.underline-gradient:hover::after {
    width: 50%;
}</style>
