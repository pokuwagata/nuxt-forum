<template>
  <div>
    <h1>forum</h1>
    <thread-form @created="createThread" />
    <h2>スレッド一覧</h2>
    <thread-list @selected="selectThread" :threads="threads" />
    <thread-view @created="createComment" :thread="selectedThread" />
  </div>
</template>

<script>
import ThreadForm from "../components/ThreadForm.vue";
import ThreadList from "../components/ThreadList";
import ThreadView from "../components/ThreadView";

export default {
  name: "App",
  components: {
    ThreadForm,
    ThreadList,
    ThreadView
  },
  data() {
    return {
      threadId: 0,
      threads: [],
      selectedThreadId: null,
      commentId: 0,
      user: null,
      commentContent: null
    };
  },
  computed: {
    selectedThread: function() {
      return this.threads[this.selectedThreadId];
    }
  },
  methods: {
    createThread: function(thread) {
      thread.id = this.threadId;
      this.threads.push(thread);
      this.threadId++;
    },
    selectThread: function(id) {
      this.selectedThreadId = id;
    },
    createComment: function(comment) {
      comment.id = this.commentId;
      this.threads[this.selectedThreadId].comments.push(comment);
      this.commentId++;
    }
  }
};
</script>
