<script setup>
import { toRefs } from 'vue';
import { Link, usePage } from '@inertiajs/vue3';

import VideoImage from 'vue-material-design-icons/VideoImage.vue'
import Image from 'vue-material-design-icons/Image.vue'
import EmoticonOutline from 'vue-material-design-icons/EmoticonOutline.vue'

import { useGeneralStore } from '@/stores/general';
import { storeToRefs } from 'pinia';
const useGeneral = useGeneralStore()
const { isPostOverlay } = storeToRefs(useGeneral)

const props = defineProps({
    image: String,
    placeholder: String,
});

const { image, placeholder } = toRefs(props)

const user = usePage().props.auth.user

</script>

<template>
    <div id="CreatePostBox" class="w-full bg-white rounded-lg px-3 mt-4 shadow-md">
        <div class="flex items-center py-3 gap-2 border-b">
            <Link>
                <img alt="" class="rounded-full ml-1 min-w-[36px] max-h-[36px]" :src="image">
            </Link>
            <div @click="isPostOverlay = true" class="flex items-center justify-start cursor-pointer p-2 rounded-full w-full bg-[#eff2f5]">
                <div class="text-left pl-2">
                    {{ placeholder }}
                </div>
            </div>
        </div>

        <div class="flex items-center py-3 border-b">
            <button class="flex items-center justify-center p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <VideoImage :size="35" fillColor="#f1284b"/>
                <div class="text-[#6f7275] font-bold">Live Vídeo</div>
            </button>
            <button class="flex items-center justify-center p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <Image :size="35" fillColor="#f1284b"/>
                <div class="text-[#6f7275] font-bold">Vídeos/Fotos</div>
            </button>
            <button class="flex items-center justify-center p-1 hover:bg-[#F2F2F2]  transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <EmoticonOutline :size="35" fillColor="#f1284b"/>
                <div class="text-[#6f7275] font-bold">Atividades/Sentimentos</div>
            </button>
        </div>
    </div>
</template>
