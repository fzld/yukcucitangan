<template>
    <nuxt-link
        :key="post.id"
        :to="post.id">
            <div class="card">
                <div class="card-content">
                    <div class="media">
                        <div class="media-content">
                        <p class="title is-4">{{ title }}</p>
                        <p class="subtitle is-6">{{ preview }}</p>
                        <p class="subtitle is-7">Klik untuk membaca lebih lanjut.</p>
                        </div>
                    </div>
                </div>
            </div>
        </nuxt-link>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        preview: {
            type: String,
            required: true
        },
        id: {
            type: String,
            required: true
        }
    }
}
</script>