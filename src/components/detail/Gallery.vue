<script setup>
import { ref } from 'vue'

const defaultImage = ref('gallery-1.png');
const galleries = ref([
    { id: 1, image: 'gallery-2.png' },
    { id: 2, image: 'gallery-3.png' },
    { id: 3, image: 'gallery-4.png' },
    { id: 4, image: 'gallery-5.png' }
]);

</script>
<template>
    <section id="gallery">
        <img :src="'/img/' + defaultImage" alt="" class="w-full mt-6 rounded-2xl">
        <div class="grid grid-cols-4 gap-4 mt-4">
            <template v-for="picture in galleries">
                <div class="overflow-hidden cursor-pointer rounded-2xl">
                    <img :src="'/img/' + picture.image" class="w-full" alt="">
                </div>
            </template>
            <!-- <div class="overflow-hidden cursor-pointer rounded-2xl ring-2 ring-indigo-500">
                <img src="/img/gallery-2.png" class="w-full" alt="">
            </div>
            <div class="overflow-hidden cursor-pointer rounded-2xl">
                <img src="/img/gallery-3.png" class="w-full" alt="">
            </div>
            <div class="overflow-hidden cursor-pointer rounded-2xl">
                <img src="/img/gallery-4.png" class="w-full" alt="">
            </div>
            <div class="overflow-hidden cursor-pointer rounded-2xl">
                <img src="/img/gallery-5.png" class="w-full" alt="">
            </div> -->
        </div>
    </section>
</template>