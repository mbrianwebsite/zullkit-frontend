<script setup>
import Card from "@/components/home/newitems/Card.vue";
import { ref, onMounted } from 'vue';
import axios from 'axios'

const items = ref([])

async function getItems() {
    try {
        const response = await axios.get('https://zullkit-backend.buildwithangga.id/api/products')
        // console.log(response.data)
        items.value = response.data.data.data
    } catch (error) {
        console.error(error);
    }
}

onMounted(() => {
    getItems();
})

// const cards = ref([
//     { title: 'Mobile UI Kit', image: 'items-1.jpg', category: 'Mobile UI Kit' },
//     { title: 'Online Doctor Consultation', image: 'items-2.jpg', category: 'Web UI Kit' },
//     { title: 'Banking Crypto', image: 'items-3.jpg', category: 'Mobile UI Kit' },
// ])

</script>
<template>
    <div class="container px-4 mx-auto my-16 md:px-12">
        <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
        <div class="flex flex-wrap -mx-1 lg:-mx-4">
            <template v-for="item in items" :key="item.id">
                <Card :title="item.name" :category="item.category.name" :image="item.thumbnails" />
            </template>
            <!-- <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
                <div class="overflow-hidden border border-gray-200 rounded-xl">
                    <a href="details.html">
                        <div class="m-4 overflow-hidden rounded-xl">
                            <img alt="Placeholder" class="block w-full h-auto" src="@/assets/img/items-2.jpg" />
                        </div>
                    </a>

                    <header class="px-4 mb-4 leading-tight">
                        <h1 class="text-lg">
                            <a class="font-semibold text-black no-underline hover:underline" href="#">
                                Online Doctor Consultation
                            </a>
                        </h1>
                        <span class="block text-sm font-light text-gray-500 no-underline">
                            Website UI Kit
                        </span>
                    </header>
                </div>
            </div>
            <div class="w-full px-1 my-1 md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
                <div class="overflow-hidden border border-gray-200 rounded-xl">
                    <a href="details.html">
                        <div class="m-4 overflow-hidden rounded-xl">
                            <img alt="Placeholder" class="block w-full h-auto" src="@/assets/img/items-3.jpg" />
                        </div>
                    </a>

                    <header class="px-4 mb-4 leading-tight">
                        <h1 class="text-lg">
                            <a class="font-semibold text-black no-underline hover:underline" href="#">
                                Banking Crypto
                            </a>
                        </h1>
                        <span class="block text-sm font-light text-gray-500 no-underline">
                            Mobile UI Kit
                        </span>
                    </header>
                </div>
            </div> -->
        </div>
    </div>
</template>