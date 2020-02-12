<template>
  <form v-on:submit.prevent="handleOnClick">
    <div>
      <label for="user-name">ユーザ名</label>
      <input type="text" id="user-name" v-model="user" />
    </div>
    <textarea id="user-content" v-model="content"></textarea>
    <button style="display: block;">書き込む</button>
  </form>
</template>
<script>
export default {
  name: "CommentForm",
  data() {
    return {
      user: null,
      content: null
    };
  },
  methods: {
    handleOnClick: function() {
      this.$emit("created", {
        user: this.user,
        content: this.content
      });
      this.user = null;
      this.content = null;
    }
  }
};
</script>
