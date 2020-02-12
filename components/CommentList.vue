<template>
  <div>
      <h4>コメント一覧</h4>
      <ul v-if="comments.length > 0">
        <li v-for="comment in comments">
          {{ comment.user }} : {{ comment.content }}
        </li>
      </ul>
      <comment-form @created="create"/>
  </div>
</template>
<script>
import CommentForm from './CommentForm';

export default {
  name: "CommentList",
  components: {
    CommentForm
  },
  props: {
    comments: Array
  },
  methods: {
    create: function(comment) {
      this.$emit("created", comment);
    }
  }
};
</script>
