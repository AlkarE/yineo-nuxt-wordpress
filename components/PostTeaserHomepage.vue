<template>
  <div>
    <div class="columns">
      <div class="column is-one-third">
        <img v-if="post.featured_media_url" :src="post.featured_media_url" />
      </div>
      <div class="column">
        <h2 v-html="post.title.rendered"></h2>
        <PostDate :date="post.date" />
        <div class="content" v-html="post.excerpt.rendered"></div>
        <div>
          <BulmaButtonLink :to="{ name: 'blog-slug', params: { slug: post.slug, post: post } }"> Lire l'article </BulmaButtonLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BulmaButtonLink from './BulmaButtonLink'
import PostDate from './PostDate'
export default {
  components: { BulmaButtonLink, PostDate },
  props: {
    post: { type: Object, default: {} }
  }
}
</script>