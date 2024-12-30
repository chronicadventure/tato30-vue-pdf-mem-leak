<template>
  <VPdfViewer :src="link"></VPdfViewer>
</template>

<script setup>

import { VPdfViewer } from '@vue-pdf-viewer/viewer';

const link = 'https://retailgptstorage.blob.core.windows.net/retaildocs/walmart-supply-chain-packaging-guide-20240131.pdf';
</script>