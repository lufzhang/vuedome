<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
        <Add :addcomment="addcomment"/>
        <List :comments="comments" :deletecomment="deletecomment"/>
    </div>
  </div>
</template>

<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'
  export default {
    data () {
      return {
        comments:[
          {
            name:"bob",
            content:"Vue bucuo"
          },
          {
            name:"cat",
            content:"Vue easy"
          },
          {
            name:"bz",
            content:"Vue soso"
          },          
        ]
      }
    },
    methods: {
      // 添加评论
      addcomment(comment){
        this.comments.unshift(comment)
      },
      // 删除评论
      deletecomment(index){
        this.comments.splice(index,1)
      },
    },
    components: {
      Add,
      List
    }
  }
</script>


<style>

</style>
