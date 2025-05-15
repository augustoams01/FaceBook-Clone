<script setup>

import { toRefs, reactive } from 'vue';
import { Link, router } from '@inertiajs/vue3';

import AccountMultiple from 'vue-material-design-icons/AccountMultiple.vue'
import ThumbUp from 'vue-material-design-icons/ThumbUp.vue'
import Check from 'vue-material-design-icons/Check.vue'
import Delete from 'vue-material-design-icons/Delete.vue'

import { useGeneralStore } from '@/stores/general';
import { storeToRefs } from 'pinia';
const useGeneral = useGeneralStore()
const { isImageDisplay } = storeToRefs(useGeneral)

const form = reactive({ comment: null })

// const props = defineProps({
//     user: Object,
//     post: Object,
//     comments: Object,
// });

// const { post, user, comments } = toRefs(props)

</script>

<template>
 <div id="Post" class="w-full bg-white rounded-lg my-4 shadow-md">
        <div class="flex items-center py-3 px-3">
            <button class="mr-2">
                <img class="rounded-full ml-1 min-w-[42px] max-h-[42px]" src="https://picsum.photos/id/140/300/320" >
            </button>
            <div class="flex items-center justify-between p-2 rounded-full w-full">
                <div>
                    <div class="font-extrabold text-[15px]">Augusto Alexandre</div>
                    <div class="flex items-center text-xs text-gray-600">
                        Enviado a 1 hora <AccountMultiple class="ml-1" :size="15" fillColor="#64676B"/>
                    </div>
                </div>
                <div class="flex items-center">
                    <button class="rounded-full p-1.5 cursor-pointer hover:bg-[#F2F2F2]">
                        <Delete fillColor="#64676B"/>
                    </button>
                </div>
            </div>
        </div>
        <div class="px-5 pb-2 text-[17px] font-semibold">Hoje fui ao mercado e achei essa íncrivel promocão de carnes vermelhas!</div>
        <img class="mx-auto cursor-pointer w-full" src="https://picsum.photos/id/140/300/320">
        <div id="Likes" class="px-5">
            <div class="flex items-center justify-between py-3 border-b">
                <ThumbUp fillColor="#1D72E2" :size="16"/>
                <div class="text-sm text-gray-600 font-semibold">70 comentários</div>
            </div>
        </div>
        <div id="Comments" class="px-3">

            <div id="CreateComment" class="flex items-center justify-between py-2">
                <div class="flex items-center w-full">
                    <Link class="mr-2">
                        <img class="rounded-full ml-1 min-w-[36px] max-h-[36px]" src="https://picsum.photos/id/140/300/320">
                    </Link>
                    <div class="flex items-center justify-center bg-[#EFF2F5] p-2 rounded-full w-full">
                        <input
                            class="
                                w-full
                                mx-1
                                border-none
                                p-0
                                text-sm
                                bg-[#EFF2F5]
                                placeholder-[#64676B]
                                ring-0
                                focus:ring-0
                            "
                            placeholder="Write a public comment..."
                            type="text"
                        >
                        <button
                            type="button"
                            class="flex items-center text-sm pl-2 pr-3.5 rounded-full bg-blue-500 hover:bg-blue-600 text-white font-bold"
                        >
                            <Check fillColor="#FFFFFF" :size="20"/> Send
                        </button>
                    </div>
                </div>
            </div>

            <div id="Comments" class="max-h-[120px] overflow-auto pb-2 px-4">
                <div
                    class="flex items-center justify-between pb-2"
                >
                    <div class="flex items-center w-full mb-1">
                        <Link class="mr-2">
                            <img class="rounded-full ml-1 min-w-[36px] max-h-[36px]" src="https://picsum.photos/id/140/300/320">
                        </Link>
                        <div class="flex items-center w-full">
                            <div class="flex items-center bg-[#EFF2F5] text-xs p-2 rounded-lg w-full">
                               texto que eu estou digitando agora
                            </div>
                            <button
                                class="rounded-full p-1.5 ml-2 cursor-pointer hover:bg-[#F2F2F2]"
                            >
                                <Delete fillColor="#64676B"/>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
