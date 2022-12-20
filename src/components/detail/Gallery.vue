<script setup>
import { ref } from "vue";
const props = defineProps({
    image: String,
    galleries: Array,
});


</script>

<template>

    <section id="gallery">
        <img :src="image" alt="" class="w-full mt-6 rounded-2xl" />
        <div v-if="galleries" class="grid grid-cols-4 gap-4 mt-4">
            <template v-for="gallery in galleries" :key="gallery.id">
                <div @mouseover="image = gallery.url" class="overflow-hidden cursor-pointer rounded-2xl"
                    :class="{ 'ring-2 ring-indigo-500': image == gallery.url }">
                    <img :src="gallery.url" class="w-full" alt="" />
                </div>
            </template>
        </div>
    </section>
</template>