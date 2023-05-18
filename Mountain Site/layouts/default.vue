<template>
    <div class="h-20 bg-blue-400 dark:text-white dark:bg-purple-400 shadow-lg flex justify-between items-center px-6">
        <div class="text-2xl cursor-pointer select-none">
            <h1 class="flex gap-2 text-center font-semibold relative" @click="toggleMode()">
                <i class="z-0 material-icons text-gray-200 items-center" v-if="isDark">dark_mode</i>
                <i class="z-0 material-icons text-yellow-100 items-center" v-else>light_mode</i>
                <i class="z-10 -top-5 left-1 absolute material-icons text-gray-500 dark:text-gray-900 text-6xl items-center">landscape</i>
                <span class="z-10">Mountains</span>
            </h1>
        </div>
        <div class="gap-4 hidden sm:flex">
            <NuxtLink class="px-4 py-2 bg-blue-500 dark:bg-purple-500 rounded-md" to="/">Home</NuxtLink>
            <NuxtLink class="px-4 py-2 bg-blue-500 dark:bg-purple-500 rounded-md" to="mountains">Explore</NuxtLink>
        </div>
    </div>

    <div class="h-[80vh] overflow-y-auto">
        <slot />
    </div>

    <footer class="py-6 bg-blue-400 dark:text-white dark:bg-purple-400 shadow-lg sm:hidden flex justify-evenly items-center">
        <NuxtLink class="px-4 py-2 bg-blue-500 dark:bg-purple-500 rounded-md" to="/">Home</NuxtLink>
        <NuxtLink class="px-4 py-2 bg-blue-500 dark:bg-purple-500 rounded-md" to="mountains">Explore</NuxtLink>
    </footer>
    
</template>

<script setup>
import {useDark, useToggle} from '@vueuse/core';

const isDark = useDark();
const toggleMode = useToggle(isDark);
const modelActive = ref(null);
const toggleModel = () => {
    modelActive.value = !modelActive.value;
};
</script>

<style scoped>

</style>