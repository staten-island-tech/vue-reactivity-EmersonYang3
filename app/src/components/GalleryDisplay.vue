<template>
  <main class="bg-white relative overflow-hidden">
    <div class="dots-background">
      <div class="gallery flex flex-row flex-wrap gap-4 p-6 justify-center">
        <div v-for="artPiece in artPieceList">
          <ArtPiece :artPieceData="artPiece" />
        </div>
        <div v-if="artPieceList.length === 0">
          <p class="text-center text-2xl font-indie text-gray-800">
            No art pieces to display! Try adding some of yours...
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import ArtPiece from './ArtPiece.vue'

interface artPieceData {
  imageSource: string
  description: string
}

defineProps<{
  artPieceList: artPieceData[]
}>()
</script>

<style lang="css" scoped>
/*
.dots-background {
  position: absolute;
  background-image: radial-gradient(circle, rgba(0, 0, 0, 1) 1px, transparent 1px);
  background-size: 30px 30px;
  animation: fadeIn 1s ease-in-out forwards;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
  */
</style>
