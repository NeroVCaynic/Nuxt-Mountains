<template>
    <div class="mx-auto container mt-8">
        <div class="flex flex-col sm:flex-row gap-4 sm:gap-2 my-4 mx-2 dark:text-white" v-for="mountain in mountains" :key="mountain.title">
            <img class="rounded-lg object-cover w-80 aspect-video" :src="mountain.image" :alt="mountain.title">
            <div>
                <h1 class="font-bold text-blue-500 dark:text-purple-500">{{ mountain.title }}- {{ mountain.height }}</h1>
                <span class="font-semibold">{{ mountain.countries[0] }}, {{ mountain.continent }}</span>
                <div class="h-32 my-2 sm:mr-2 md:mr-6 overflow-hidden overflow-y-auto">
                    {{ mountain.description }}
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>

const { data:mountains } = await useFetch("https://api.nuxtjs.dev/mountains");
console.log(mountains)

</script>

<style lang="scss" scoped>

</style>