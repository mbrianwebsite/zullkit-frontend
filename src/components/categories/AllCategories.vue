<script setup>
import Card from "@/components/home/categories/Card.vue";
import { ref, onMounted } from 'vue';
import axios from 'axios'

const categories = ref([])

async function getCategories() {
    try {
        const response = await axios.get('https://zullkit-backend.buildwithangga.id/api/categories')
        // console.log(response.data)
        categories.value = response.data.data.data
    } catch (error) {
        console.error(error);
    }
}

onMounted(() => {
    getCategories();
})

// const cards = ref([
//     { title: 'Mobile UI Kit', image: 'categories-1.jpg', items: 731 },
//     { title: 'Fonts', image: 'categories-2.jpg', items: 657 },
//     { title: 'Icon Set', image: 'categories-3.jpg', items: 83559 },
//     { title: 'Web UI Kit', image: 'categories-4.jpg', items: 4500 }
// ])

</script>
<template>
    <div class="container px-4 mx-auto my-16 md:px-12">
        <h2 id="CategoryList" class="mb-4 text-xl font-medium md:mb-0 md:text-lg">
            All Categories
        </h2>
        <div class="flex flex-wrap -mx-1 lg:-mx-4">
            <Card v-for="category in categories" :key="category.id" :id="category.id" :title="category.name"
                :items="category.products_count" :image="category.thumbnails" />
        </div>
    </div>
</template>