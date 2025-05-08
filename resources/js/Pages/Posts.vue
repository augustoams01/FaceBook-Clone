<script setup>

import { Head, Link, usePage } from '@inertiajs/vue3';
import MainNavLayout from '@/Layouts/MainNavLayout.vue';
import CreatePostBox from '@/Components/CreatePostBox.vue';

import Magnify from 'vue-material-design-icons/Magnify.vue'
import TelevisionPlay from 'vue-material-design-icons/TelevisionPlay.vue'
import StorefrontOutline from 'vue-material-design-icons/StorefrontOutline.vue'
import AccountGroup from 'vue-material-design-icons/AccountGroup.vue'
import AccountMultiple from 'vue-material-design-icons/AccountMultiple.vue'
import Flag from 'vue-material-design-icons/Flag.vue'
import ClockTimeTwoOutline from 'vue-material-design-icons/ClockTimeTwoOutline.vue'
import Restore from 'vue-material-design-icons/Restore.vue'
import VideoImage from 'vue-material-design-icons/VideoImage.vue'
import DotsHorizontal from 'vue-material-design-icons/DotsHorizontal.vue'

const user = usePage().props.auth.user
</script>

<template>
    <Head title="Posts" />

    <MainNavLayout>
        <div class="fixed w-full h-[100%] bg-[#F1F2F5]">
            <div class="grid grid-rows-3 grid-flow-col w-full  mt-[76px] h-[calc(100%-56px)] mx-auto px-4">
                <div id="LeftSection" class="xl:w-[345px] lg:block hidden">
                    <div class="flex flex-col gap-4 px-4 py-4 w-full bg-white/60 rounded-md">
                        <Link href="/" class="flex items-center justify-start w-full cursor-pointer bg-sky-400 hover:bg-sky-500 transition duration-300 p-2 rounded-md">
                            <img src="https://picsum.photos/id/8/300/320" alt="" class="rounded-full ml-1 min-w-[38px] max-h-[38px]">
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Augusto Alexandre</div>
                        </Link>
                        <!--Criar posteriormente leftMenuCard com props-->
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <AccountMultiple :size="40" fillColor="#5BD7C6"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Friends</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <Flag :size="40" fillColor="#F2682C"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Pages</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <ClockTimeTwoOutline :size="40" fillColor="#21AAFA"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Most Recent</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <AccountGroup :size="40" fillColor="#20A9FD"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Groups</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <StorefrontOutline :size="40" fillColor="#48C0D8"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Marketplace</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <TelevisionPlay :size="40" fillColor="#9739CF"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Watch</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md transition duration-300">
                            <Restore :size="40" fillColor="#32B4D0"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Memories</div>
                        </button>
                    </div>
                </div>

                <div id="PostsSection" class="row-span-6 max-w-[600px] lg:mx-0 mx-auto overflow-auto">

                    <CreatePostBox image="https://picsum.photos/id/8/300/320" placeholder="O que você está pensando Augusto Alexandre?"/>

                </div>

                <div id="RightSection" class="pl-4 md:block hidden ">
                    <div class="max-w-[500px] min-w-[250px] ml-auto pt-4 bg-white/60 px-10 rounded-md h-[500px] mb-4">
                        <div class="flex items-center justify-between border-b border-b-gray-300">
                            <div class="font-semibold">Contacts</div>
                            <div class="flex items-center">
                                <div class="p-2 hover:bg-gray-300 rounded-full cursor-pointer">
                                    <VideoImage :size="23" fillColor="#050505"/>
                                </div>
                                <div class="p-2 hover:bg-gray-300 rounded-full cursor-pointer">
                                    <Magnify :size="23" fillColor="#050505"/>
                                </div>
                                <div class="p-2 hover:bg-gray-300 rounded-full cursor-pointer">
                                    <DotsHorizontal :size="23" fillColor="#050505"/>
                                </div>
                            </div>
                        </div>
                        <div class="h-[400px] overflow-auto pt-2">
                            <!--Criar posteriormente RightContactCard com props-->
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/140/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Andrew Smith</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Wade Konopelski</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/142/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Thora Deckow</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/135/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Prof. Cooper Ratke</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/140/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Dennis Hackett</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Jodie Collins</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/142/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Alphonso Lindgren</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/149/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Barrett Fay Jr</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/140/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Andrew Smith</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Wade Konopelski</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/142/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Thora Deckow</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Prof. Cooper Ratke</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/140/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Dennis Hackett</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Jodie Collins</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/142/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Alphonso Lindgren</div>
                            </div>
                            <div class="flex items-center justify-start cursor-pointer hover:bg-[#E5E6E9] py-2 rounded-md">
                                <img class="rounded-full ml-1 min-w-[38px] max-h-[38px]" src="https://picsum.photos/id/141/300/320">
                                <div class="text-[15px] text-gray-800 font-extrabold pl-3">Barrett Fay Jr</div>
                            </div>
                        </div>
                    </div>

                    <div class="max-w-[500px] min-w-[250px] ml-auto pt-4 bg-white/60 px-10 rounded-md h-[300px]">
                        <div class="flex items-center justify-between border-b border-b-gray-200">
                            <div class="font-semibold">Visto Recentemente</div>
                            <div class="flex items-center">
                                <div class="p-2 hover:bg-gray-300 rounded-full cursor-pointer">
                                    <Magnify :size="23" fillColor="#050505"/>
                                </div>
                                <div class="p-2 hover:bg-gray-300 rounded-full cursor-pointer">
                                    <DotsHorizontal :size="23" fillColor="#050505"/>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
            </div>
        </div>
    </MainNavLayout>

</template>
