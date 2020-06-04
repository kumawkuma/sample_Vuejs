<template>
  <div id="comment">
    <form @submit.prevent="addComment">
      <input type="text" v-model="newComment" />
      <input type="submit" value="Tweet" />
    </form>

    <ul v-if="comments.length">
      <li v-for="(comment,index) in comments" :key="comment">
        <input type="checkbox"/>
        {{ comment }}
        <span
          @click="deleteComment(index)"
          id="command"
        >[delete!]</span>
      </li>
    </ul>
    <ul v-else>
      <li class="start">Let's Tweet Now!</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "commentForm",
  data: function() {
    return {
      newComment: "",
      comments: [],
      readComment:false
    };
  },
  methods: {
    addComment() {
     
      this.comments.push(this.newComment);
      this.newComment = "";
    },
    deleteComment(index) {
      this.comments.splice(index, 1);
    }
  }
};
</script>

<style>
ul {
  list-style: none;
  margin: 40px auto;
  padding-right: 50px;
}
span {
  cursor: pointer;
}
input {
  font-family: "Courier New", Courier, monospace;
  margin: 5px;
}
#command {
  color: rgb(156, 144, 144);
}
.start {
  font-weight: bold;
  font-size: larger;
}
#comment li > span.read {
  text-decoration: line-through;
  color: #bbb;
}
</style>