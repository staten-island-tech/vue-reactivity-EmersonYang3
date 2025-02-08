<template>
  <figure class="w-86 max-w-full border p-2 bg-white">
    <div class="relative pb-[56.25%]">
      <img
        :src="artPieceData.imageSource"
        alt="Art piece"
        class="absolute inset-0 w-full h-full object-cover border"
      />
    </div>
    <figcaption class="text-right italic font-indie">
      {{ '-' + artPieceData.description }}
    </figcaption>
  </figure>
</template>

<script setup lang="ts">
interface ArtPieceData {
  imageSource: string
  description: string
}

defineProps<{
  artPieceData: ArtPieceData
}>()
</script>
