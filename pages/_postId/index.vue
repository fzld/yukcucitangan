<template>
    <div class="container">
        <h1 class="title">{{ title }}</h1>
        <p class="subtitle">{{ previewText }}</p>
        <p class="subtitle">{{ content }}</p>
        <p class="subtitle">{{ paragraph2 }}</p>
        <p class="subtitle">{{ paragraph3 }}</p>
        <p class="subtitle">{{ paragraph4 }}</p>
        <p class="subtitle">{{ paragraph5 }}</p>
        <p class="subtitle">{{ paragraph6 }}</p>
        <p class="subtitle">{{ paragraph7 }}</p>
        <p class="subtitle">{{ paragraph8 }}</p>
        <p class="subtitle">{{ paragraph9 }}</p>
        <p class="subtitle">{{ paragraph10 }}</p>
        

        <div class="footer">
            &copy; 2020 #YukCuciTangan
            <br>
            Data dari API <a href="https://github.com/mathdroid">@mathdroid</a>
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
                title: res.data.story.content.title,
                previewText: res.data.story.content.previewText,
                content: res.data.story.content.content,
                paragraph2: res.data.story.content.paragraph2,
                paragraph3: res.data.story.content.paragraph3,
                paragraph4: res.data.story.content.paragraph4,
                paragraph5: res.data.story.content.paragraph5,
                paragraph6: res.data.story.content.paragraph6,
                paragraph7: res.data.story.content.paragraph7,
                paragraph8: res.data.story.content.paragraph8,
                paragraph9: res.data.story.content.paragraph9,
                paragraph10: res.data.story.content.paragraph10
            }
        })
    }
}
</script>