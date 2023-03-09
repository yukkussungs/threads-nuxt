<template>
    <MainLayout>
        <div class="w-full overflow-auto" id="IndexPage">
            <div class="mx-auto max-w-[500px] overflow-hidden">
                <div id="Posts" class="px-4 max-w-[600px] mx-auto">
                    <div class="text-white" v-if="isPosts" v-for="post in posts" :key="post">
                        {{ post }}
                    </div>
                </div>
            </div>
        </div>
    </MainLayout>
</template>

<script setup>
import { onBeforeMount } from 'vue';
import MainLayout from '~/layouts/MainLayout.vue';

import { useUserStore } from '../stores/user';
const userStore = useUserStore();

let posts = ref([])
let isPosts = ref(true)
let isLoading = ref(false)

onBeforeMount(() => {
    posts.value = [
        {
            name: 'Shin Woosung',
            image: 'https:/placehold.co/100',
            text: 'This is the title',
            picture: 'https:/placehold.co/500',
        }
    ]
});
</script>

<style lang="sass" scoped>

</style>