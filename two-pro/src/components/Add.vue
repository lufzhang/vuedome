<template>
    <div class="col-md-4">
        <form class="form-horizontal">
          <div class="form-group">
            <label>用户名</label>
            <input type="text" class="form-control" placeholder="用户名" v-model="name">
          </div>
          <div class="form-group">
            <label>评论内容</label>
            <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
          </div>
          <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
              <button type="button" class="btn btn-default pull-right" @click="add">提交</button>
            </div>
          </div>
        </form>
    </div>
</template>

<script>
  export default {
    props: {
      addcomment:{
        // 指定属性名，属性值的类型，必要性
        type:Function,
        required:true,
      }
    },
    data () {
      return {
        name:"",
        content:""  
      }
    },
    methods: {
      add(){
        // 1、检查输入的合法性
        const name = this.name.trim()
        const content = this.content.trim()
        // 这里trim是去除空格符号
        if(!name||!content){
          // 双杠是或者的意思，不符合name或者content则执行
          alert("no kong")
          return
        }
        // 2、根据输入的数据，封装一个comment对象
        const comment = {
          name,
          content
        }
        // 3、添加到comments中
        // 数据在哪个组件，更新数据的方式就应该在哪个组件，comments在app组件
        this.addcomment(comment)
        // 4、清楚输入
        this.name=""
        this.content=""
      }
    }
  }
</script>


<style>

</style>