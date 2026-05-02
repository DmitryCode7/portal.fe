<template>
    <h2>
        {{ article.title }}
    </h2>
    <p>
        {{ article.content }}
    </p>
    <img :src="article.image" alt=""  height='750px' v-if="article.image";>
    
</template>

<script>
import axios from 'axios';
    export default {
        data() {
            return {
                articleId: this.$route.params.id,
                article: {}
            }
        },
        mounted() {
            this.loadArticle();
        },
        methods: {
            async loadArticle() {
                const response = await axios.get("http://portal.be/api/articles/" + this.articleId);
                this.article = response.data;
            }
        },
        wath: {
            "$route.params.id": function (newId) {
                this.articleId = newId;
                this.loadArticle();
            }
        }
    }
</script>

<style>
    body {
        background-image: url("https://static.vecteezy.com/system/resources/previews/023/385/832/large_2x/nature-of-green-leaf-in-garden-at-summer-natural-green-leaves-plants-using-as-spring-background-cover-page-greenery-environment-ecology-wallpaper-generate-ai-free-photo.jpg");
        background-size: cover;
        color: white;
    }
    img {
        
    }
</style>