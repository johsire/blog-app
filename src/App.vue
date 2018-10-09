
<template>
  <div>
    <h1>Coding Dojo with Joh</h1>

    <button @click="toogle">Toggle Menu</button>

    <section v-if="showForm">
      <h3>Crate Post</h3>
      <p>Author: <input type="text" v-model="author"></p>
      <textarea name="" id="" cols="30" rows="10" v-model="postInput"></textarea>
      <button @click="addPost">Submit</button>
    </section>

    <section v-else>
      <h3>Blog Posts</h3>
      <post v-for="(post, i) in blogPosts" :key="i" :postObj="post"></post>

    </section>

  </div>
</template>

<script>
import Post from './components/Post';


export default {
  data: function() {
    return {
      showForm: true,
      author: '',
      postInput: '',
      blogPosts: ''
    }
  },
  methods: {
    toogle: function() {
      this.showForm = !this.showForm;
    },
    addPost: function() {
      if (!this.author || !this.postInput) {
        alert('Please fill out the entire form!');
        return;
      }
      this.blogPosts.push({
        name: this.author,
        post: this.postInput
      });
      this.author = '';
      this.postInput = '';
      this.toogle();
    }
  },
  components: {
    post: Post
  },
  created() {
    console.log('created')
  },
  mounted() {
    // axios calls go here
  }
}
</script>
