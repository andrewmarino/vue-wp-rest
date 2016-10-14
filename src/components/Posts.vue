<template>
  <ul class="posts">
    <li v-for="post in posts">
      <article>
        <h2>{{ post.title.rendered }}</h2>
        <div class="post-content" v-html="post.content.rendered"></div>
      </article>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    }
  },
  methods: {
    fetchPosts() {
      let self = this;
      let url = '/wp-json/wp/v2/posts/';
      let xhr = new XMLHttpRequest();
      xhr.open('GET', url, true);
      xhr.onload = function() {
        if (xhr.status >= 200 && xhr.status < 400) {
          self.posts = JSON.parse(xhr.responseText);
        } else {
          // We reached our target server, but it returned an error
        }
      };
      xhr.send();
    }
  },
  mounted() {
    this.fetchPosts();
  }
}
</script>

<style>
</style>
