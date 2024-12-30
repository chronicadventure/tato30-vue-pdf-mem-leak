<template>
    <button @click="loadPdf = !loadPdf">{{ loadPdf ? 'Unload' : 'Load' }}</button>

    <div v-if="loadPdf">
        <div v-for="(page, index) in pages">
            <VuePDF :pdf="pdf" :page="page" auto-destroy></VuePDF>
        </div>
    </div>

</template>

<script setup>
const loadPdf = ref(false);

import { VuePDF, usePDF } from '@tato30/vue-pdf';

const { pdf, pages } = usePDF('https://retailgptstorage.blob.core.windows.net/retaildocs/walmart-supply-chain-packaging-guide-20240131.pdf');


</script>