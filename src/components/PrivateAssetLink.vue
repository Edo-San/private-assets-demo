<template>
  <div v-editable="blok">
    <a :href="privateAssetURL" target="_blank" rel="noopener noreferrer"
      >Download private asset</a
    >
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({ blok: Object });

const privateAssetURL = computed(
  () =>
    `${import.meta.env.VITE_SERVERLESS_BASE_PATH}${
      import.meta.env.VITE_SERVERLESS_DOWNLOAD_PRIVATE_ASSET_ENDPOINT
    }?assetURL=${props.blok.asset.filename}`
);

// console.log(privateAssetURL.value);

// const privateAssetURL = `${import.meta.env.VITE_SERVERLESS_BASE_PATH}${
//   import.meta.env.VITE_SERVERLESS_DOWNLOAD_PRIVATE_ASSET_ENDPOINT
// }?assetURL=${this.blok.asset.filename}`;
</script>
