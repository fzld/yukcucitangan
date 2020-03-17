<template>
    <div class="container">
        <h1 class="title">Blog</h1>
        <p class="subtitle">Informasi untuk kalian semua.</p>
        <hr>
        
        <nuxt-link
        v-for="post in posts"
        :key="post.id"
        :to="post.id">
            <div class="card">
                <div class="card-content">
                    <div class="media">
                        <div class="media-content">
                        <p class="title is-3">{{ post.title }}</p>
                        <p class="subtitle is-6">{{ post.previewText }}</p>
                        <p class="subtitle is-7 has-text-right">Posted on {{ post.date }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </nuxt-link>

        <div class="footer">
            &copy; 2020 #YukCuciTangan 
            <br>
            Data dari API <a href="https://github.com/mathdroid">@mathdroid</a>
        </div>
    </div>
</template>

<script>
export default {
    asyncData(context){
        return context.app.$storyapi.get('cdn/stories', {
            version: 'draft',
            starts_with: 'blog/'
        })
        .then(res => {
            return {
                posts: res.data.stories.map(bp => {
                return {
                    id: bp.slug,
                    title: bp.content.title,
                    previewText: bp.content.previewText,
                    date: bp.created_at
                }
            })
            };
        })
    },
    head: {
    title: 'Blog #YukCuciTangan',
    meta: [
      {  
      }
    ]}
}
</script>