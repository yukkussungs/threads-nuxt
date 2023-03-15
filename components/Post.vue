<template>
    <div class="z-50 bottom-0 h-full w-full">
        <div class="py-2 w-full">
            <div class="flex items-center justify-between">
                <div class="flex items-center text-white">
                    <img :src="post.image" alt="" class="rounded-full h-[35px]">
                    <div class="ml-2 font-semibold text-[18px]">{{ post.name }}</div>
                </div>

                <div @click="isMenu = !isMenu" class="relative">
                    <button 
                        :disabled="isDeleting"
                        class="flex items-center text-white p-1 h-[24px] w-[24px] hover:bg-gray-800 rounded-full cursor-pointer" 
                        :class="isMenu ? 'bg-gray-800' : ''"
                    >
                        <Icon v-if="!isDeleting" name="bi:three-dots" color="#ffffff" size="18"/>
                        <Icon v-else name="eos-icons:bubble-loading" color="#ffffff" size="18"/>
                    </button>
                    <div v-if="isMenu" class="absolute border border-gray-600 right-0 z-20 mt-1 rounded">
                        <button
                            class="flex items-center rounnded gap-2 text-red-500 justify-between bg-black w-full pl-4 pr-3 py-1 hover:bg-gray-900"
                        >
                        <div>Delete</div>
                        <Icon name="solar:trash-bin-trash-broken" size="20" />
                    </button>
                    </div>
                </div>
            </div>
            <div class="relative flex items-center w-full">
                <div class="w-[42px] mx-auto">
                    <div class="absolute ml-4 mt-1 top-0 w-[1px] bg-gray-700 h-full"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { useUserStore } from '~/store/user';
const userStore = useUserStore();

const runtimeConfig = useRuntimeConfig();
let isMenu = ref(false)
let isLike = ref(false)
let isDeleting = ref(false)
</script>

<style lang="sass" scoped>

</style>