<template>
  <main class="h-screen flex flex-col">
    <TheHeader />
    <section class="flex flex-1 flex-row">
      <FormPreview class="w-s" @submitArt="AppendArt" />
      <GalleryDisplay class="flex-1" :artPieceList="artPieceList" />
    </section>
  </main>
</template>

<script setup lang="ts">
import TheHeader from '@/components/TheHeader.vue'
import FormPreview from '@/components/FormPreview.vue'
import GalleryDisplay from '@/components/GalleryDisplay.vue'

import { reactive } from 'vue'

interface ArtPieceData {
  imageSource: string
  description: string
}

const artPieceList = reactive<ArtPieceData[]>([])

function AppendArt(artPieceData: { imageSource: string; description: string }) {
  artPieceList.push({
    imageSource: artPieceData.imageSource,
    description: artPieceData.description,
  })
}
</script>
