<template>
  <form v-on:submit.prevent="handleOnClick">
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
</template>
<script>
export default {
  name: "ThreadForm",
  data() {
    return {
      threadName: null,
      threadContent: null
    };
  },
  methods: {
    handleOnClick: function() {
      this.$emit("created", {
        name: this.threadName,
        content: this.threadContent,
        comments: []
      });
      this.threadName = null;
      this.threadContent = null;
    }
  }
};
</script>
