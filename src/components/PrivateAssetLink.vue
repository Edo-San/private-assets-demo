<template>
  <div v-editable="blok">
    <a
      :href="privateAssetURL"
      target="_blank"
      rel="noopener noreferrer"
      class="private-asset-link"
    >
      Download private asset
    </a>
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
</script>

<style scoped>
.private-asset-link {
  font-family: Arial, Helvetica, sans-serif;
  color: darkslateblue;
  padding: 0.75rem;
  text-decoration: none;
  border: 2px solid darkslateblue;
  border-radius: 0.5rem;
  transition: all 0.3s;
}

.private-asset-link:hover {
  color: white;
  background-color: darkcyan;
  border-color: darkcyan;
}
</style>
