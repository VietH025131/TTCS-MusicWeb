<script setup>
import { ref, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import MenuItem from './components/MenuItem.vue'
import MusicPlayer from './components/MusicPlayer.vue'
import ChevronUp from 'vue-material-design-icons/ChevronUp.vue'
import ChevronDown from 'vue-material-design-icons/ChevronDown.vue'
import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue'
import ChevronRight from 'vue-material-design-icons/ChevronRight.vue'

import { useSongStore } from './stores/song'
import { storeToRefs } from 'pinia'
const useSong = useSongStore()
const { isPlaying, currentTrack } = storeToRefs(useSong)

onMounted(() => {
  isPlaying.value = false
})
let openMenu = ref(false)
</script>

<template>
  <div>
    <div
      class="w-[calc(100%-240px)] h-[60px] fixed right-0 z-20 bg-[#101010] bg-opacity-80 flex items-center justify-between"
    >
      <div class="flex items-center ml-6">
        <button type="button" class="rounded-full bg-black p-[1px] cursor pointer">
          <ChevronLeft fillColor="#FFFFFF" :size="30" />
        </button>
        <button type="button" class="rounded-full bg-black p-[1px] ml-4 cursor pointer">
          <ChevronRight fillColor="#FFFFFF" :size="30" />
        </button>
      </div>
      <button
        @click="openMenu = !openMenu"
        :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
        class="bg-black hover:bg-[#282828] rounded-full p-0.5 mr-8 cursor-pointer"
      >
        <div class="flex items-center">
          <img
            class="rounded-full"
            width="27"
            src="https://yt3.ggpht.com/yti/AHyvSCB0n-BwC0nLI9cWx2crhWvjWs40KHnWMyAWNFH5lg=s88-c-k-c0x00ffffff-no-rj-mo"
            alt=""
          />
          <div class="text-white text-[14px] ml-1.5 font-semibold">Viet</div>
          <ChevronDown v-if="!openMenu" @click="openMenu = true" fillColor="#FFFFFF" :size="25" />
          <ChevronUp v-else @click="openMenu = false" fillColor="#FFFFFF" :size="25" />
        </div>
      </button>
      <span
        v-if="openMenu"
        class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer"
      >
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3e3d3d] border-b border-b-gray-600">Profile</li>
          <li class="px-3 py-2.5 hover:bg-[#3e3d3d]">Log Out</li>
        </ul>
      </span>
    </div>
    <div id="sidenav" class="h-[100%] p-6 w-[240px] fixed z-50 bg-black">
      <RouterLink to="/"
        ><div class="flex items-center justify-center h-20 bg-black text-white">
          <div class="flex items-center justify-center h-20 w-20 bg-white text-white rounded-full">
            <img src="public/images/icons/logo.png" class="w-50 h-80" />

            <!-- Additional logo content can be added here -->
          </div>
          <h1 class="text-3xl font-bold">Musica</h1>
          <!-- <div class="flex items-center bg-white">
            <img
              src="public/images/icons/logo.png"
              viewBox="0 0 24 24"
              fill="#ffffff"
              class="w-20 h-20"
            />
          </div>
          <h1 class="ml-2 text-2xl font-bold text-gray-500">Musica</h1>
          Logo content will be added here -->
        </div>
      </RouterLink>
      <div class="my-8"></div>
      <ul>
        <RouterLink to="/">
          <MenuItem class="ml-[1px]" :iconSize="23" name="Home" iconString="home" pageUrl="/" />
        </RouterLink>
        <RouterLink to="/search">
          <MenuItem
            class="ml-[1px]"
            :iconSize="24"
            name="Search"
            iconString="search"
            pageUrl="/search"
          />
        </RouterLink>
        <RouterLink to="/library">
          <MenuItem
            class="ml-[2px]"
            :iconSize="23"
            name="Library"
            iconString="library"
            pageUrl="/library"
          />
        </RouterLink>
        <div class="py-3.5"></div>
        <MenuItem :iconSize="24" name="Create Playlist" iconString="playlist" pageUrl="/playlist" />
        <MenuItem
          class="ml-[1px]"
          :iconSize="27"
          name="Liked Songs"
          iconString="liked"
          pageUrl="/liked"
        />
      </ul>
      <div class="border-b border-b-gray-700"></div>
      <ul>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">
          My Playlist #1
        </li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">
          My Playlist #2
        </li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">
          My Playlist #3
        </li>
        <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white">
          My Playlist #4
        </li>
      </ul>
    </div>
    <div
      class="fixed right-0 top-0 w-[calc(100%-240px)] overflow-auto h-full bg-gradient-to-b from-[#1C1C1C] to-black"
    >
      <div class="mt-[70px]"></div>
      <RouterView />
      <div class="mb-[100px]"></div>
    </div>
  </div>

  <MusicPlayer v-if="currentTrack" />
</template>

<style scoped></style>
