<script setup>
// import dos ícones da lib vue-material-design-icons para consumo na aplicação
    import { ref } from 'vue';
    import { Link, usePage } from '@inertiajs/vue3';
    // import CreatePostOverlay from '@/Components/CreatePostOverlay.vue'
    // import ImageDisplay from '@/Components/ImageDisplay.vue';

    import Magnify from 'vue-material-design-icons/Magnify.vue'
    import Home from 'vue-material-design-icons/Home.vue'
    import HomeOutline from 'vue-material-design-icons/HomeOutline.vue'
    import TelevisionPlay from 'vue-material-design-icons/TelevisionPlay.vue'
    import StorefrontOutline from 'vue-material-design-icons/StorefrontOutline.vue'
    import AccountGroup from 'vue-material-design-icons/AccountGroup.vue'
    import ControllerClassicOutline from 'vue-material-design-icons/ControllerClassicOutline.vue'
    import DotsGrid from 'vue-material-design-icons/DotsGrid.vue'
    import FacebookMessenger from 'vue-material-design-icons/FacebookMessenger.vue'
    import Bell from 'vue-material-design-icons/Bell.vue'
    import Logout from 'vue-material-design-icons/Logout.vue'

    // import CropperModal from '@/Components/CropperModal.vue';

    import { useGeneralStore } from '@/stores/general';
    import { storeToRefs } from 'pinia';
    const useGeneral = useGeneralStore()
    const { isPostOverlay, isCropperModal, isImageDisplay } = storeToRefs(useGeneral)

    const user = usePage().props.auth.user

    let showMenu = ref(false)

</script>


<!-- 
-layout usado para a construção da página inicial.
-está sendo consumido pelo posts.vue
-->

<template>
    <div id="MainNav" class="fixed z-50 w-full flex items-center justify-between h-[56px] bg-white shadow-xl border-b">

        <div id="NavLeft" class="flex items-center justify-start w-[260px]">
            <Link href="/" class="pl-3 min-w-[55px]">
                FB
            </Link>
            <div class="flex items-center justify-center bg-[#EFF2F5] p-1 rounded-full h-[40px] ml-2">
                <Magnify class="p-1" :size="22" fillColor="#64676B"/>
                <input type="text" placeholder="Pesquisar" class="lg:block hidden border-none p-0 bg-[#EFF2F5] placeholder-[#64676B] ring-0 focus:ring-0">
            </div>
        </div>
        <div id="NavCenter" class="hidden lg:flex items-center ml-5 justify-center w-8/12 max-w-[600px]">
            <Link class="w-full" :href="route('posts.index')">
                <div
                    :class="$page.url === '/' ? 'mt-1.5' : '' "
                    class="flex items-center justify-center h-[48px] p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg cursor-pointer"
                >
                    <div>
                        <Home v-if="$page.url === '/'" class="mx-auto" :size="27" fillColor="#38bdf8"/>
                        <HomeOutline v-else class="mx-auto" :size="32" fillColor="#38bdf8"/>
                    </div>
                </div>
                <div
                    v-if="$page.url === '/'"
                    class="border-b-4 border-b-sky-400 rounded-md"
                ></div>
            </Link>
            <button class="flex items-center justify-center h-[48px] p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <TelevisionPlay class="mx-auto" :size="27" fillColor="#64676B"/>
            </button>
            <button class="flex items-center justify-center h-[48px] p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <StorefrontOutline class="mx-auto" :size="27" fillColor="#64676B"/>
            </button>
            <button class="flex items-center justify-center h-[48px] p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <span class="rounded-full border-[2px] border-[#64676B] p-1">
                    <AccountGroup class="mx-auto" :size="22" fillColor="#64676B"/>
                </span>
            </button>
            <button class="flex items-center justify-center h-[48px] p-1 hover:bg-[#F2F2F2] transition duration-300 w-full rounded-lg mx-1 cursor-pointer">
                <ControllerClassicOutline class="mx-auto" :size="32" fillColor="#64676B"/>
            </button>
        </div>
        <div class="flex items-center justify-end w-2/12 mr-4">
            <button class="rounded-full bg-[#E3E6EA] p-2 hover:bg-gray-300 mx-1 transition duration-300 cursor-pointer">
                <DotsGrid :size="23" fillColor="#050505"/>
            </button>
            <button class="rounded-full bg-[#E3E6EA] p-2 hover:bg-gray-300 mx-1 transition duration-300 cursor-pointer">
                <FacebookMessenger :size="23" fillColor="#050505"/>
            </button>
            <button class="rounded-full bg-[#E3E6EA] p-2 hover:bg-gray-300 mx-1 transition duration-300 cursor-pointer">
                <Bell :size="23" fillColor="#050505"/>
            </button>
            <div class="flex items-center justify-center relative">
                <button @click="showMenu = !showMenu">
                    <img src="https://picsum.photos/id/8/300/320" alt="" class="rounded-full ml-1 min-w-[40px] max-w-[40px] cursor-pointer">
                </button>
                <div v-if="showMenu" class="absolute bg-white shadow-xl top-10 right-0 w-[330px] rounded-lg p-1 border mt-3">
                    <Link href="/" @click="showMenu = !showMenu">
                        <div class="flex items-center gap-3 hover:bg-gray-200 p-2 rounded-lg">
                            <img src="https://picsum.photos/id/8/300/320" alt="" class="rounded-full ml-1 min-w-[35px] max-w-[35px] cursor-pointer">
                            <span>Augusto Alexandre</span>
                        </div>
                    </Link> 
                    <Link class="w-full" :href="route('logout')" as="button" method="post">
                        <div class="flex items-center gap-3 hover:bg-gray-200 p-2 rounded-lg py-2.5">
                            <Logout class="pl-2" :size="30"/>
                            <span>Sair</span>
                        </div>
                    </Link>  
                    <div class="text-xs font-semibold p-2 pt-3 border-t mt-1">
                        Privacy · Terms · Advertising · Ad Choices · Cookies · SpaceLab © 2025
                    </div>
                </div>
            </div>
        </div>
        
    </div>

    <slot/>
</template>
