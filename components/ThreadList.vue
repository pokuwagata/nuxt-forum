<template>
  <div>
    <ul>
      <li v-for="thread in threads" v-on:click="selectThread(thread.id)">
        <a href="" v-on:click.prevent>{{ thread.name }}</a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "ThreadList",
  props: {
    threads: Array
  },
  methods: {
    selectThread: function(id) {
      this.$emit("selected", id);
    }
  }
};
</script>
