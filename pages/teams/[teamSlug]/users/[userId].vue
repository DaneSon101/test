<template>
    <div>
        <h1>{{ message }}</h1>
    </div>
</template>

<script setup>
    const route = useRoute()
    const message = computed(() => `Im on team ${ route.params.teamSlug } and my user id is ${ route.params.userId }`)
</script>