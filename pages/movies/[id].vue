<script setup>
const route = useRoute()
const { data, error } = await useFetch(
  `https://www.omdbapi.com/?apikey=7ef4e65b&i=${route.params.id}`,
  
  {
  pick:['Plot', 'Title', 'Awards', "Error", "Poster"],
  key: `/movies/${route.params.id}`,
}
)
if(data.value.Error === "Incorrect IMDb ID.") {
  showError({statusCode: 404, statusMessage: "Page Not Found"})
}

useHead({
  title: data.value.Title,
  meta:[
    { name: "description", content: data.value.Plot },
    { property:'og:description', content: data.value.Plot },
  { property: 'og:image', content:data.value.Poster }
  ]
})

// const { data } = useAsyncData(
//   `/movies/${route.params.id}`,
//   ()=> {
//   return $fetch(
//     `https://www.omdbapi.com/?apikey=7ef4e65b&i=${route.params.id}`
//     )
// },{
// pick:['Plot', 'Title', 'Awards']
// })

// const res = await $fetch(
//     `https://www.omdbapi.com/?apikey=7ef4e65b&i=${route.params.id}`
//     )

</script>

<template>
    <div>
        <pre>{{ data }}</pre>
    </div>
</template>
