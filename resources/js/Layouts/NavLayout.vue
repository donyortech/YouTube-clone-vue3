<script setup>
import { ref } from "vue";
import { Link } from "@inertiajs/vue3";
import SideNavItem from "../Components/SideNavItem.vue";
import MenuIcon from "vue-material-design-icons/Menu.vue";
import MagnifyIcon from "vue-material-design-icons/Magnify.vue";

let openSideNav = ref(true);
</script>

<template>
    <div class="relative">
        <div
            id="TopNav"
            class="w-[100%] h-[60px] fixed bg-black z-20 flex items-center justify-between"
        >
            <div class="flex items-center">
                <button
                    @click="openSideNav = !openSideNav"
                    class="p-2 ml-3 rounded-full hover:bg-gray-800 inline-block cursor-pointer"
                >
                    <MenuIcon fillColor="#FFFFFF" :size="26" />
                </button>
                <div class="mx-2"></div>
                <Link
                    class="flex items-center justify-center mr-10 cursor-pointer"
                >
                    <img class="" width="32" src="/images/YT-logo.png" alt="" />
                    <img width="62" src="/images/YT-logo-text.png" alt="" />
                </Link>
            </div>
            <div class="w-[600px] md:block hidden">
                <div class="rounded-full flex items-center bg-[#222222]">
                    <input
                        type="text"
                        class="form-control block w-full px-5 py-1.5 text-base font-normal text-gray-200 bg-black placeholder-gray-400 bg-clip-padding border border-solid border-l-gray-700 border-y-gray-700 rounded-l-full transition ease-in-out m-0 border-transparent focus:ring-0"
                        placeholder="Search"
                    />
                    <MagnifyIcon
                        class="mx-6 cursor-pointer"
                        fillColor="#FFFFFF"
                        :size="23"
                    />
                </div>
            </div>
            <div>
                <img
                    class="rounded-full mx-8 cursor-pointer"
                    width="35"
                    src="https://yt3.ggpht.com/pqnZ1ZIWaaQrJLfFpHN3AublCwjsKeby5d5I6ND5HrX4RxzKsulRG3NQZKj2kIfrtKDZIGu9qA=s88-c-k-c0x00ffffff-no-rj-mo"
                />
            </div>
        </div>
        //new content 15.05.2023
        <div
            id="SideNav"
            :class="[!openSideNav ? 'w-[70px]' : 'w-[240px]']"
            class="h-[100%] fixed z-0 bg-black"
        >
            <ul
                :class="[!openSideNav ? 'p-2' : 'px-5 pb-2 pt-[7px]']"
                class="mt-[60px] w-full"
            >
                <SideNavItem :openSideNav="openSideNav" iconString="Home" />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Add Video"
                />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Delete Video"
                />
                <div class="border-b border-b-gray-700 my-2.5"></div>
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Subscriptions"
                />
                <SideNavItem :openSideNav="openSideNav" iconString="Library" />
                <SideNavItem :openSideNav="openSideNav" iconString="Liked" />
                <SideNavItem :openSideNav="openSideNav" iconString="History" />
                <SideNavItem
                    :openSideNav="openSideNav"
                    iconString="Watch Later"
                />
                <div v-if="openSideNav">
                    <div class="border-b border-b-gray-700 my-2.5">
                        <div class="text-gray-400 text-[14px] text-extrabold">
                            About Press Copyright
                            <div>Contact us</div>
                            Creator Advertise Developers
                        </div>
                        <div class="border-b border-b-gray-700 my-2.5"></div>
                        <div class="text-gray-400 text-[14px] text-extrabold">
                            Terms Privacy Policy & Safety
                            <div>How YouTube works</div>
                            <span>Test new features</span>
                        </div>
                    </div>
                </div>
            </ul>
        </div>
        <div id="SideNavOverlay"></div>
        <slot />
    </div>
</template>

<style>
body {
    background-color: black;
}
</style>
