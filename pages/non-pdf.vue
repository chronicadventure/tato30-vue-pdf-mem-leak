<template>
    <ul>
        <li v-for="(n, index) in Array.from({ length: 1000 })" :key="index">
            Item {{ index + 1 }}
        </li>
    </ul>
</template>

<script setup>

</script>