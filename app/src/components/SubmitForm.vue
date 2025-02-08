<template>
  <form @input="updatePreview" class="space-y-6">
    <div class="space-y-2">
      <label for="imageSource" class="block text-sm font-medium text-gray-700 font-indie"
        >Image Source URL</label
      >
      <input
        id="imageSource"
        type="text"
        placeholder="https://example.com/image.jpg"
        required
        v-model="urlSource"
        class="w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 hover:border-gray-400 font-indie text-gray-700 placeholder-gray-400 transition-all 0.15s ease-in-out"
      />
    </div>
    <div class="space-y-2">
      <label for="description" class="block text-sm font-medium text-gray-700 font-indie"
        >Description</label
      >
      <textarea
        id="description"
        placeholder="Describe your art piece..."
        required
        v-model="description"
        rows="3"
        class="w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 hover:border-gray-400 font-indie text-gray-700 placeholder-gray-400 transition-all 0.15s ease-in-out resize-none"
      ></textarea>
    </div>
  </form>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(['updatePreview'])
const urlSource = ref('')
const description = ref('')

function updatePreview() {
  emit('updatePreview', { imageSource: urlSource.value, description: description.value })
}
</script>
