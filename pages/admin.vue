<template>
    <div>
        hello users
    </div>
</template>

<script setup>
definePageMeta({
    middleware:['auth']
})
</script>