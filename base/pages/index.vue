<template>
    <h1>VueUse Nuxt layer issue reproduction</h1>

    <p>Mouse is {{ pressed ? '' : 'not' }} pressed</p>
</template>

<script setup lang="ts">
const { pressed } = useMousePressed();
</script>