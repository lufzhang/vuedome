<template>
    <li class="list-group-item">
        <div class="handle">
            <a href="javascript:;" @click="dele">删除</a>
        </div>
        <p class="user"><span>{{comment.name}}</span><span>说:</span></p>
        <p class="centence">{{comment.content}}</p>
    </li>
</template>

<script>
export default {
    props: {
        // 这里用这种方法，可以调用它的内部数据，如comment.name
        comment:Object,
        deletecomment:Function,
        index:Number,
    },
    methods: {
        dele(){
            const {comment,deletecomment,index} = this
            if (window.confirm("queding ${comment.name}")) {
                deletecomment(index)
            }  
        },
    }
}
</script>


<style>
    li {
        transition: .5s;
        overflow: hidden;
    }

    .handle {
        width: 40px;
        border: 1px solid #ccc;
        background: #fff;
        position: absolute;
        right: 10px;
        top: 1px;
        text-align: center;
    }

    .handle a {
        display: block;
        text-decoration: none;
    }

    .list-group-item .centence {
        padding: 0px 50px;
    }

    .user {
        font-size: 22px;
    }
</style>