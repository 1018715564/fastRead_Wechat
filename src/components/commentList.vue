<template>
  <div class="comment-list">
    <div class="page-title" v-show="comment.length">评论</div>
    <div class="comment" v-for="comment in comment" :key="comment._id">
      <div class="user">
        <div class="inline">
          <img :src="comment.avatarUrl" class="avatar" mode="aspectFit">
          {{comment.name}}
        </div>
        <div class="right">
          {{comment.location||'未知地点'}}
          <span class="text-primary">--</span>
          {{comment.phone||'未知型号'}}
        </div>
      </div>
      <div class="content">{{comment.comment}}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['comment'],
  mounted () {
    console.log('评论' + this.comment)
  }
}
</script>

<style lang="stylus" scoped>
.comment-list {
  background: #eee;
  font-size: 14px;

  .comment {
    background: white;
    margin-bottom: 10px;
    padding: 5px 20px;

    .content {
      margin: 10px 0;
    }

    .user {
      .inline {
        display: inline;

        .avatar {
          width: 20px;
          height: 20px;
          border-radius: 50%;
          vertical-align: middle;
        }
      }
    }
  }
}
</style>
