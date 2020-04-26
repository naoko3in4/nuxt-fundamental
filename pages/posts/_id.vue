<template>
  <div class="container">
    <article>
      <h1 class="title">
        {{ post.title }}
      </h1>
      <p>
        {{ post.content }}
      </p>
    </article>
    <aside>
      <h5>Posts you might enjoy</h5>
      <ul>
        <li v-for="related in relatedPosts">
          <nuxt-link :to="{name: 'posts-id', params:{id: related.id}}">
            {{ related.title }}
          </nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.id,
      posts: [
        {
          id: 'balut',
          title: 'What is Balut?',
          content: 'If someone placed balut on your plate, you might think they were serving you a hardboiled egg.'
        },
        {
          id: 'whereIsIt',
          title: 'Where is the signs in button??',
          content: 'I\'ve stalked the forum for a while, reading everything closely, but today I decided that it was time to register as a user. So I did'
        },
        {
          id: 'how',
          title: 'How can I fix this problem?',
          content: 'Please help me. I don\'t know what is the best way to fix my problem. I cant reproduce and I cant tell more info. Can someone help me asap?'
        },
      ]
    }
  },
  computed: {
    post() {
      return this.posts.find(post => post.id === this.id)
    },
    relatedPosts() {
      return this.posts.filter(post => post.id !== this.id)
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
  line-height: 1.5;
}

article * {
  margin-bottom: 1rem;
}

aside {
  min-width: 200px;
  max-width: 200px;
}
</style>