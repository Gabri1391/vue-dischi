<template>
   <div class="col album-card">
        <div class="albums-card text-center p-2">
            <img class="img-fluid mb-3" :src="image" :alt="title" />
            <h4 class="text-white">{{ title }}</h4>
            <div class="author text-secondary">{{ author }}</div>
            <div class="year text-secondary">{{ year }}</div>
         </div>
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props:{
        image: String,
        title: String,
        author: String,
        year: String,
    },

}
</script>

