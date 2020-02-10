<template>
  <div>
    <h1>forum</h1>
    <form v-on:submit.prevent="createThred">
      <div>
        <label for="thread-name">スレッド名</label>
        <input type="text" id="thread-name" v-model="threadName" />
      </div>
      <div>
        <label for="thread-content">内容</label>
        <textarea id="thread-content" v-model="threadContent"></textarea>
      </div>
      <button>スレッド作成</button>
    </form>
    <h2>スレッド一覧</h2>
    <div>
      <ul>
        <li v-for="thread in threads" v-on:click="selectThread(thread.id)">
          <a href="" v-on:click.prevent>{{ thread.name }}</a>
        </li>
      </ul>
    </div>
    <div v-if="selectedThread">
      <h3>{{ selectedThread.name }}</h3>
      <p>{{ selectedThread.content }}</p>
      <h4>コメント一覧</h4>
      <ul v-if="selectedThread.comments.length > 0">
        <li v-for="comment in selectedThread.comments">
          {{ comment.user }} : {{ comment.content }}
        </li>
      </ul>
      <form v-on:submit.prevent="createComment">
        <div>
          <label for="user-name">ユーザ名</label>
          <input type="text" id="user-name" v-model="user"/>
        </div>
        <textarea id="user-content" v-model="commentContent"></textarea>
        <button style="display: block;">書き込む</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hoge",
  data() {
    return {
      threadId: 0,
      threadName: null,
      threadContent: null,
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
    createThred: function() {
      this.threads.push({
        id: this.threadId,
        name: this.threadName,
        content: this.threadContent,
        comments: []
      });
      this.threadId++;
    },
    selectThread: function(id) {
      this.selectedThreadId = id;
    },
    createComment: function() {
      this.threads[this.selectedThreadId].comments.push({
        id: this.commentId,
        user: this.user,
        content: this.commentContent
      });
      this.commentId++;
    }
  }
};
</script>
