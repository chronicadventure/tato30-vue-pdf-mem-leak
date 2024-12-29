<template>
    <h3>
        <div v-for="(page, index) in pages">
            <VuePDF :pdf="pdf" :page="page"></VuePDF>
        </div>
       
    </h3>
</template>

<script setup>

import { VuePDF, usePDF } from '@tato30/vue-pdf';


const { pdf, pages } = usePDF('https://retailgptstorage.blob.core.windows.net/retaildocs/walmart-supply-chain-packaging-guide-20240131.pdf');

onUnmounted(async () => {

if (pdf.value && typeof pdf.value.destroy === 'function') {
  console.log('Destroying PDF document');
  await pdf.value.destroy();
}

if (pdf.value && pdf.value._worker && pdf.value._worker._webWorker) {
  console.log('worker terminated');
  pdf.value._worker._webWorker.terminate(); // Terminate the worker manually
} else {
  console.log('could not find worker', pdf.value);
}

pdf.value = null;
})
</script>