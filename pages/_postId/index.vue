<template>
    <div class="container" v-editable="blok">
        <h1 class="title">{{ title }}</h1>
        <p class="subtitle">{{ previewText }}</p>
        <p class="subtitle">{{ content }}</p>
        <p class="subtitle">{{ paragraph2 }}</p>
        <p class="subtitle">{{ paragraph3 }}</p>
        

        <div class="footer">
            &copy; 2020 #YukCuciTangan
            <br>
            Data dari API <a href="https://github.com/mathdroid">@mathdroid</a><br>
            Reponya <a href="https://github.com/fzld/yukcucitangan">disini</a> ya, hehe.
        </div>
    </div>
</template>

<script>
export default {
    asyncData(context) {
        return context.app.$storyapi.get('cdn/stories/blog/' + context.params.postId, {
            version: 'draft'
        }).then(res => {
            return {
                blok: res.data.story.content,
                title: res.data.story.content.title,
                previewText: res.data.story.content.previewText,
                content: res.data.story.content.content,
                paragraph2: res.data.story.content.paragraph2,
                paragraph3: res.data.story.content.paragraph3,
            }
        })
    }
}
</script>