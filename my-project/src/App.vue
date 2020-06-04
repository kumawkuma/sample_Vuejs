<template>
  <div id="app">
    <input type="text" v-model="name" class="name" />
    <p>
      Hello {{ name }}!
      total:{{ total }}
    </p>
      <likeButton v-on:increment="GoodAndBut"> 
      </likeButton><likeButton message="But" v-on:increment="GoodAndBut"></likeButton>
  
      <commentForm></commentForm>
  </div>
</template>

<script>
import likeButton from "./components/likeButton";
import commentForm from "./components/commentForm";

export default {
  name: "App",
  components: { likeButton, commentForm },
  data: function() {
    return {
      name: "-  please Your name here  -",
      total: 0
    };
  },
  methods: {
    GoodAndBut() {
      this.total++;
    }
  }
};
</script>

<style>
#app {
  font-family: "Courier New", Courier, monospace;
  padding-top: 50px;
  margin: 0 auto;
  text-align: center;
}
.name {
  font-family: "Courier New", Courier, monospace;
  width: 30em;
  text-align: center;
}
</style>