<template>
    <h1>VueUse Nuxt layer issue reproduction</h1>

    <p>Mouse is {{ pressed ? '' : 'not' }} pressed</p>

    <p>{{ camelCased }}</p>
</template>

<script setup lang="ts">
// VueUse composables work in the base layer but are not found in the sublayer
const { pressed } = useMousePressed();

// Lodash functions work in the sublayer as expected
const camelCased = useCamelCase('hello-world');
</script>