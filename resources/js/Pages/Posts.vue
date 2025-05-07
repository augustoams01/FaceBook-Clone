<script setup>

import { Head, Link, usePage } from '@inertiajs/vue3';
import MainNavLayout from '@/Layouts/MainNavLayout.vue';

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
            <div class="grid grid-rows-3 grid-flow-col w-full max-w-[1600px] mt-[56px] h-[calc(100%-56px)] mx-auto px-4">
                <div id="LeftSection" class="xl:w-[345px] lg:block hidden">
                    <div class="pt-4 max-w-[320px] pr-4">
                        <Link href="/" class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] p-2 rounded-md">
                            <img src="https://picsum.photos/id/8/300/320" alt="" class="rounded-full ml-1 min-w-[38px] max-h-[38px]">
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Augusto Alexandre</div>
                        </Link>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <AccountMultiple :size="40" fillColor="#5BD7C6"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Friends</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <Flag :size="40" fillColor="#F2682C"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Pages</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <ClockTimeTwoOutline :size="40" fillColor="#21AAFA"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Most Recent</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <AccountGroup :size="40" fillColor="#20A9FD"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Groups</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <StorefrontOutline :size="40" fillColor="#48C0D8"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Marketplace</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <TelevisionPlay :size="40" fillColor="#9739CF"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Watch</div>
                        </button>
                        <button class="flex items-center justify-start w-full cursor-pointer hover:bg-[#E5E6E9] px-2 py-1.5 rounded-md">
                            <Restore :size="40" fillColor="#32B4D0"/>
                            <div class="text-[15px] text-gray-800 font-extrabold pl-3">Memories</div>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </MainNavLayout>

</template>
