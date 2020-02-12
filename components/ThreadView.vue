<template>
    <div v-if="thread">
      <h3>{{ thread.name }}</h3>
      <p>{{ thread.content }}</p>
      <comment-list @created="create" :comments="thread.comments"/>
    </div>
</template>
<script>
import CommentList from "./CommentList";
export default {
  name: "ThreadView",
  components: {CommentList},
  props: {
    thread: Object
  },
  methods: {
    create: function(comment) {
      this.$emit("created", comment);
    }
  }
};
</script>
