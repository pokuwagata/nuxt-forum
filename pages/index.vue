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
      {{ threads[selectedThread].content }}
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
      selectedThread: null
    };
  },
  methods: {
    createThred: function() {
      this.threads.push({
        id: this.threadId,
        name: this.threadName,
        content: this.threadContent
      });
      this.threadId++;
    },
    selectThread: function(id) {
      this.selectedThread = id;
    }
  }
};
</script>
