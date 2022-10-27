<template>
    <Header />
    <h1>test</h1>
    <!-- <span>{{data}}</span> -->
    <ul>
        <li v-for="item in data" :key="item.id" class="item">
            <!-- {{item}} -->
            <div class="title">{{item.title}}</div>
            <div class="description">{{item.description}}</div>
            <div class="height">{{item.height}}</div>
            <div class="countries">{{item.countries}}</div>
            <div class="continent">{{item.continent}}</div>
            <div class="image">{{item.image}}</div>
            <div class="dir">{{item.dir}}</div>
            <div class="path">{{item.path}}</div>
            <div class="slug">{{item.slug}}</div>
            <div class="updatedAt">{{item.updatedAt}}</div>
        </li>
    </ul>
    <Footer />
</template>

<script setup>
// export default {

// }
const { data, pending, error, refresh } = await useAsyncData(
  'mountains',
  () => $fetch('https://api.nuxtjs.dev/mountains')
)
</script>

<style scoped>
    .item{
        display: block;
        list-style-type: none;
        margin-bottom: 50px;
        border: 1px solid black;
        padding: 10px;
        border-radius: 10px;
    }
</style>