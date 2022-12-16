<script setup>
import Card from "@/components/home/categories/Card.vue";
import { ref, onMounted } from 'vue';
import axios from 'axios'

const categories = ref([])

async function getCategories() {
    try {
        const response = await axios.get('https://zullkit-backend.buildwithangga.id/api/categories?show_product=1&limit=4')
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
            Top Categories
        </h2>
        <div class="flex flex-wrap -mx-1 lg:-mx-4">
            <template v-for="category in categories" :key="category.id">
                <Card :id="category.id" :title="category.name" :items="category.products_count"
                    :image="category.thumbnails" />
            </template>
            <!-- <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/4">
                <div class="overflow-hidden border border-gray-200 rounded-xl">
                    <a href="details.html">
                        <div class="m-4 overflow-hidden rounded-xl">
                            <img alt="Placeholder" class="block w-full h-auto" src="@/assets/img/categories-2.jpg" />
                        </div>
                    </a>

                    <header class="px-4 mb-4 leading-tight">
                        <h1 class="text-lg">
                            <a class="font-semibold text-black no-underline hover:underline" href="#">
                                Fonts
                            </a>
                        </h1>
                        <span class="block text-sm font-light text-gray-500 no-underline">
                            657 items
                        </span>
                    </header>
                </div>
            </div>
            <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/4">
                <div class="overflow-hidden border border-gray-200 rounded-xl">
                    <a href="details.html">
                        <div class="m-4 overflow-hidden rounded-xl">
                            <img alt="Placeholder" class="block w-full h-auto" src="@/assets/img/categories-3.jpg" />
                        </div>
                    </a>

                    <header class="px-4 mb-4 leading-tight">
                        <h1 class="text-lg">
                            <a class="font-semibold text-black no-underline hover:underline" href="#">
                                Icon Set
                            </a>
                        </h1>
                        <span class="block text-sm font-light text-gray-500 no-underline">
                            83,559 items
                        </span>
                    </header>
                </div>
            </div>
            <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/4">
                <div class="overflow-hidden border border-gray-200 rounded-xl">
                    <a href="details.html">
                        <div class="m-4 overflow-hidden rounded-xl">
                            <img alt="Placeholder" class="block w-full h-auto" src="@/assets/img/categories-4.jpg" />
                        </div>
                    </a>

                    <header class="px-4 mb-4 leading-tight">
                        <h1 class="text-lg">
                            <a class="font-semibold text-black no-underline hover:underline" href="#">
                                Website UI Kit
                            </a>
                        </h1>
                        <span class="block text-sm font-light text-gray-500 no-underline">
                            4,500 items
                        </span>
                    </header>
                </div>
            </div> -->
        </div>
    </div>
</template>