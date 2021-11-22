<template>
  <section id="comments" class="bg-comments">
    <div class="title">
      <h2>COMMENTS</h2>
    </div>
    <div class="row">
      <div class="add-comment-form column">
        <form class="comment-form" @submit.prevent="addNewItem">
          <p>You can add your comment</p>
          <input
            required
            name="name"
            v-model="newUserName"
            placeholder="Name"
            type="text"
            autocomplete="off"
          />
          <br />

          <textarea
            name="message"
            v-model="newCommentText"
            rows="4"
            placeholder="Comment"
            required
          ></textarea>
          <br />
          <button class="button" @click="addNewComment">Add Comment</button>
        </form>
      </div>
      <div class="comment-list column">
        <div v-if="comments.length === 0" style="margin: 0 auto">
          <p id="comment-state">There are no comments</p>
        </div>
        <div
          v-else
          class="comment-card"
          style="display: flex"
          v-for="(comment, index) in comments"
          :key="index"
        >
          <img id="user-img" src="../assets/user.png" alt="" />
          <div id="comment-info">
            <h2 style="font-weight: 600">{{ comment.user_name }}</h2>
            <p>{{ comment.user_comment }}</p>
          </div>
          <img
            id="bin-img"
            class="column-comment"
            src="../assets/bin.png"
            alt=""
            style="align: right"
            @click="removeComment(index)"
          />
          <br />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      newUserName: "",
      newCommentText: "",
      comments: [],
    };
  },
  methods: {
    addNewComment() {
      if (this.newUserName === "" && this.newCommentText === "") {
        return;
      }
      this.comments.push({
        user_name: this.newUserName,
        user_comment: this.newCommentText,
      });
      this.newUserName = "";
      this.newCommentText = "";
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    },
  },
};
</script>
<style lang="scss">
@import "@/styles/comments.scss";
</style>